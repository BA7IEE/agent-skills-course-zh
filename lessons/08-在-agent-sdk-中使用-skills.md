# 08 在 Agent SDK 中使用 Skills

## 这章讲什么

这一章进入整套课最“系统化”的部分：

> 如果你不是只想用现成产品，而是想自己做 agent 应用，skill 应该放在系统里的什么位置？

原课用的是一个研究型 agent 案例。主代理会把任务分给多个子代理：

- 文档研究
- 仓库分析
- 网络资料搜索

然后再把结果综合起来，生成某个开源工具的学习指南。

## 读这一章之前，你最好先有一个预期

这一章不会只停留在“写一个 skill 文件”。

它讨论的是更大的问题：

- 一个系统怎样分角色
- 一个主代理怎样调度子代理
- 一个 skill 怎样在复杂系统里继续保持作用

## 这里第一次出现的术语怎么理解

- `SDK`：开发工具包，可以理解成“官方给开发者准备的一组工具”
- `orchestrator` / 主代理：负责调度和汇总结果的那个 agent
- `synthesize`：把不同来源的信息综合起来，形成统一输出

## 这一章真正的价值在哪里

很多人以为这一章是在教“再高级一点的 Anthropic 用法”。其实它更重要的价值是：

它展示了 skill 在复杂系统里不是孤立存在的，而是：

- 和主代理提示词协作
- 和子代理分工协作
- 和工具调用协作
- 和外部资料来源协作

换句话说，skill 开始从“单点能力”变成“系统方法论的一部分”。

这就是为什么这一章看起来更复杂，但也更接近真正的 agent 产品设计。

## 主代理和 skill 的关系

原课里有一个很重要的设计点：

主代理会被明确告知：

- 如果提供了 skill
- 且 skill 和用户请求匹配
- 就应该严格按 skill 里的方法执行

这说明一个成熟的 agent 系统，不能把 skill 当成“可有可无的小附件”，而应该把它视为方法优先级的一部分。

原课这节里的 skill 还有一个边界特别值得记住：

- 这个 skill 是给主代理用的
- 它不是分发给每个子代理各自执行的
- 它的作用是规范主代理如何调度、如何综合，以及如何组织最终输出

## 为什么要多个子代理

因为研究类任务天然适合拆分。

比如你要学一个开源工具，信息来源就至少有三类：

- 官方文档
- GitHub 仓库
- 社区文章或视频

如果全让一个 agent 在一个上下文里完成，容易混乱，也不利于并行。拆成子代理后：

- 每个角色更专注
- 输出格式更稳定
- 主代理更容易做最后综合

这里最值得学的不是“有几个子代理”，而是“为什么这样拆”。好的拆分，不是让系统更炫，而是让结构更清楚。

## 中文场景例子

比如你想做一个“帮中文用户快速学会某开源项目”的 agent：

- 一个子代理专门看官方文档
- 一个子代理专门看 GitHub 仓库结构
- 一个子代理专门找社区教程和踩坑经验
- 主代理最后把它们整合成“中文版学习路线”

这就是原课案例在中文语境下最容易理解的映射。

## skill 在这里扮演什么角色

skill 不是来替代子代理的，而是给主代理提供一套研究方法：

- 要提取哪些信息
- 该如何组织学习结果
- 最终输出应该长什么样

这让整套系统不仅“能搜”，还能“按方法去搜、按结构来写”。

原课还展示了一个很漂亮的点：主代理在综合阶段，会继续通过渐进式披露读取额外参考文件，把研究结果整理成带层级的学习路径，而不是只把子代理的原始输出拼在一起。

## 这一章最值得带走的一个观念

当 agent 系统开始变复杂时，问题不再是“模型够不够聪明”，而是：

- 角色边界清不清楚
- 方法有没有沉淀下来
- 结果如何汇总

这时，skill 的价值反而更明显，因为它是少数能稳定传递方法的机制之一。

## 如果你以后要做自己的 agent 应用

这章至少给你三个启发：

1. 主代理要负责调度和综合，不要什么都自己做
2. 子代理要有明确边界，不要角色重叠
3. skill 要负责方法和结构，而不是替代所有提示词

## 常见误区

- 误区 1：以为子代理越多越高级
- 误区 2：以为 skill 可以代替系统架构设计
- 误区 3：主代理、子代理、skill 三者职责不分

## 本章相关链接

- [课程代码仓库（L7）](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L7)
- [主代理与子代理系统提示](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L7/prompts)
- [learning-a-tool skill 文件](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L7/.claude/skills/learning-a-tool/)
- [utils.py](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L7/utils.py)
- [agent.py](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L7/agent.py)
- [课程拍摄中生成的学习指南](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L7_notes/learning-mineru/)
- [L7 README](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L7/README.md)
- [Agent SDK：Advanced Permission Control](https://platform.claude.com/docs/en/agent-sdk/python#example-advanced-permission-control)
- [Agent SDK：Building a Continuous Conversation Interface](https://platform.claude.com/docs/en/agent-sdk/python#building-a-continuous-conversation-interface)
- [Claude Agent SDK Documentation](https://platform.claude.com/docs/en/agent-sdk/overview)
- [Python Agent SDK](https://platform.claude.com/docs/en/agent-sdk/python)
- [Agent Skills in the SDK](https://platform.claude.com/docs/en/agent-sdk/skills)
- [Claude Agent SDK Demos](https://github.com/anthropics/claude-agent-sdk-demos)

## 本章你应该带走什么

- skill 在复杂 agent 系统里仍然重要，甚至更重要
- 子代理解决的是分工，skill 解决的是方法统一
- 一个成熟的 agent 应用，通常是主代理、子代理、工具和 skill 共同构成的

## 本章练习

- 假设你要做一个“学习某开源项目”的 agent，先写出主代理和 2 到 3 个子代理的职责边界
- 再写一句话说明：这个系统里的 skill 应该负责什么，不应该负责什么

## 这章学完后可以立刻做什么

- 先不写代码，先把一个 agent 应用拆成主代理和多个角色
- 再单独写出 skill 在这个系统里的职责边界

## 这章最适合用在哪些场景

- 你准备做一个多代理协作的小系统
- 你想把“研究、分析、综合”拆成不同角色
- 你在设计 agent 产品而不是单次工具调用

## 建议产出

- 一页“角色分工草图”，包括：
  - 主代理职责
  - 子代理职责
  - skill 负责的方法部分
