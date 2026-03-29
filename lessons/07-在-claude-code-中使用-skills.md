# 07 在 Claude Code 中使用 Skills

## 这章讲什么

这一章把 skill 带回最典型的开发者场景：

> 在真实代码项目里，skill 能帮你做什么？

原课通过一个命令行待办应用，演示了：

- 项目级说明文件的作用
- 在 Claude Code 里如何组织 skills
- skills 如何配合代码生成、审查和测试
- subagent 和 skill 如何一起用

## 这一章为什么很多开发者会有共鸣

因为一旦你真的在代码库里长期和 AI 协作，就会非常明显地遇到两个问题：

- 项目背景解释不完
- 重复任务总在重新说一遍

## 这里第一次出现的词先解释一下

- [`CLAUDE.md`](../resources/examples/CLAUDE.md)：项目级长期说明文件
- `slash command`：早期的一种命令式自定义入口
- `subagent`：在主任务之外接手子任务的独立代理

而这一章展示的，正好就是如何把这两类成本降下来。

## 为什么这一章离真实工作最近

如果前几章更像“认知建立”，那这一章就是“离真实工作最近”的一章。

因为很多开发者真正关心的是：

- skill 到底能不能进项目
- 怎么让它和现有代码库一起工作
- 怎么避免每次都重新解释项目背景

## [`CLAUDE.md`](../resources/examples/CLAUDE.md) 的意义

原课展示了一个非常重要的文件：[`CLAUDE.md`](../resources/examples/CLAUDE.md)。

你可以把它理解成项目级的长期背景说明，它通常会写：

- 这个项目是做什么的
- 技术栈是什么
- 目录结构怎样组织
- 哪些约定是每次对话都应该知道的

这和 skill 的关系是：

- [`CLAUDE.md`](../resources/examples/CLAUDE.md) 负责项目级长期上下文
- skill 负责某一类任务的方法

一个偏“背景”，一个偏“流程”。

如果你把二者混在一起，通常会出现两种后果：

- 长期背景写进某个 skill，导致 skill 变得笨重
- 具体工作流写进 [`CLAUDE.md`](../resources/examples/CLAUDE.md)，导致全局上下文越来越脏

所以这一章真正有价值的地方，在于它教你怎么分层。

## 在 Claude Code 里，skill 有什么特别之处

原课里更接近工程现实的，不是“skill 突然多了什么神秘能力”，而是 Claude Code 给了它一个很适合项目协作的落点：

- 项目级 skills 可以放在 `.claude/skills/`
- 也可以有用户级 skills，放在你的 home 目录
- Claude Code 会把这些 skills 当成项目里的真实工作流资源来使用
- 你还可以把特定 skills 明确分配给某个 subagent

这说明在代码场景里，skill 不只是“提示包”，而更像项目工作流的一部分。

## 这一章最该学会的不是命令，而是组织方式

原课中的项目示范了一个很好的习惯：

- 项目背景写进长期上下文
- 具体任务方法写进 skill
- 分角色工作时再配合 subagent

这样的好处是：

- 解释成本更低
- 工作流更稳定
- 新任务更容易接入

## 换成团队协作视角来看

你可以把 Claude Code 场景里的三层信息这样看：

- 项目层：这个仓库是什么、怎么组织、有哪些共识
- 任务层：某类工作应该按什么标准执行
- 角色层：哪些工作适合交给不同的 agent 或 subagent

当这三层拆清楚后，skill 才会真正开始发挥价值。

## 中文团队场景例子

假设你们团队每次合并代码前都要做一轮固定检查：

- 看命名是否统一
- 看是否补了测试
- 看 CLI 输出是否符合团队习惯

如果这些规则只存在于某位同事脑子里，就不稳定。

把它们写进 skill，团队内的 AI 协作质量就会更一致。

## skills 和 slash commands 的关系

原课提到，在 Claude Code 里，旧的自定义 slash command 能力后来被并入了 skills。

这件事背后说明了一个趋势：

> 单纯的命令入口不够，未来更重要的是“命令 + 资源目录 + 调用控制 + 上下文策略”。

所以，skills 比早期命令系统更像一个完整的工作流容器。

原课里还有两个很实用的小细节：

- 新建 skill 后，Claude Code 通常要重启一次，才能让新 skill 被识别出来
- `/skills` 可以帮助你检查当前项目级 skills 是否已经正确加载

## 子代理怎么和 skill 配合

原课提到了两种思路：

- 给某个自定义 subagent 注入特定 skill
- 让某个 skill 总是在隔离上下文中运行

这意味着你可以做更细粒度的分工，比如：

- 代码审查子代理专门带上审查 skill
- SQL 相关子代理带上 SQL 审查 skill

这比把所有规则都塞给主代理要清晰得多。

这里还有一个非常关键的实现细节：

- subagent 不会自动继承主代理的 skills
- 你必须显式把 skill 分配给对应的 subagent
- 当 subagent 被派发时，整个 [`SKILL.md`](../resources/examples/skill-template/SKILL.md) 会预先加载进来，而不是只先放名字和描述

## 给中文开发者的一个现实建议

如果你想在自己项目里尝试，不要一开始就做一大堆 skill。

先选一个最稳定、最重复的开发任务，例如：

- 给 CLI 命令加新子命令
- 审查某类 PR
- 补某类测试

先把它 skill 化，再决定是否加 subagent 和更多工具约束。

## 常见误区

- 误区 1：把所有项目信息都塞进 [`CLAUDE.md`](../resources/examples/CLAUDE.md)
- 误区 2：把每一个小动作都做成独立 skill
- 误区 3：一开始就上很复杂的 subagent 编排

## 本章你应该带走什么

- [`CLAUDE.md`](../resources/examples/CLAUDE.md) 管项目背景，skill 管任务方法
- Claude Code 里的 skill 更贴近真实工程工作流，而且和项目目录、subagent 配置直接相关
- skill 和 subagent 配合后，能把开发流程做得更清晰、更稳定

## 本章练习

- 想一个你现在项目里最重复的开发任务，判断它应该写进 [`CLAUDE.md`](../resources/examples/CLAUDE.md) 还是写成 skill
- 如果它要进一步拆分，写出一个最简单的 subagent 分工思路

## 这章学完后可以立刻做什么

- 选一个你当前代码仓库里最重复的开发任务
- 决定它该落在项目背景层、skill 层，还是子代理层

## 这章最适合用在哪些场景

- 你已经在代码项目里和 AI 协作
- 你发现项目背景和任务规则混在一起越来越乱
- 你想把某类开发任务做成团队可复用流程

## 建议产出

- 一份简单分层草图：
  - [`CLAUDE.md`](../resources/examples/CLAUDE.md) 放什么
  - skill 放什么
  - subagent 负责什么
