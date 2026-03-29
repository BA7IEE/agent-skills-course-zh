# 01 为什么要把重复工作做成 Skill

## 这章讲什么

这一章回答一个最实际的问题：

> 为什么不直接每次写 prompt，而要把一件事整理成 skill？

原课用的是营销数据分析案例。这个例子很有代表性，因为它很像现实工作：

- 数据格式固定
- 分析步骤固定
- 输出结构固定
- 但你又要一遍遍重复说明

## 先把问题说得更直白一点

很多人以为自己遇到的是“不会写 prompt”，其实更常见的情况是：

- 你已经知道怎么描述任务
- 但这件事你要反复描述很多遍
- 而且每次描述还不能漏步骤

一旦进入这个状态，问题就不再只是“提问”，而是“流程管理”。

## 这里第一次出现的关键词怎么理解

- `Prompt`：你临时发给 AI 的一次性说明
- `Workflow`：一套有顺序、有输入输出预期的工作步骤
- `Skill`：把这套 workflow 固定下来、方便重复调用的形式

## 用大白话先讲明白

如果你经常在不同对话里反复说同一套话，比如：

- 先做数据质量检查
- 再做漏斗分析
- 然后按某个模板输出结论
- 最后补一些指标解释

那你遇到的已经不是“单次提问”问题，而是“重复工作流”问题。

一旦进入这个阶段，skill 比 prompt 更合适。因为它能把：

- 任务目标
- 步骤顺序
- 输出格式
- 参考规则

一起打包。

## 原课案例在讲什么

原课展示的是一个营销分析工作流。用户给 Claude 一份活动数据表，希望它：

- 检查数据质量
- 做漏斗分析
- 对比基准数据
- 输出指定格式的结论
- 后续再结合预算规则给出调整建议

如果每次都重新写这些要求，不仅麻烦，还容易出现这几个问题：

- 某一步忘了写
- 输出格式前后不一致
- 新对话里上下文丢了
- 团队成员各写各的，结果不统一

把它整理成 skill 后，工作方式就从“临时交代”变成了“稳定流程”。

## 中文场景例子

把营销分析换成更贴近中文用户的场景，你也许更容易理解：

- 每周整理小红书内容数据
- 每次都要先看数据缺失
- 再算互动率
- 再总结哪些选题值得继续做

如果你总在重复这套步骤，它就已经不像“随手问一句”，而更像一个应该沉淀的方法。

## 为什么这件事对中文用户尤其重要

很多中文用户使用 AI 时有一个共同习惯：先靠经验试几次 prompt，觉得“差不多能用”就停了。

这没错，但它会卡在一个阶段：

- 个人偶尔用，够了
- 一旦想稳定重复，马上开始混乱

skill 的意义，是把“会用”升级成“可重复交付”。

## 这一章和上一章的关系

上一章是在告诉你这套课要解决什么问题。

这一章开始把镜头拉近：先不谈标准、不谈目录结构，先只看一个现实判断题。

> 什么时候，一件事值得从 prompt 升级成 skill？

## 什么时候该考虑把 prompt 升级成 skill

你可以用下面这个判断方法。

如果一项工作同时满足以下 3 点，就很值得做成 skill：

- 你会反复做
- 步骤相对稳定
- 你希望输出风格一致

典型场景包括：

- 每周数据分析
- 固定标准的代码审查
- 固定模板的课程资料整理
- 固定格式的客户访谈总结

## 这一章最核心的判断

skill 不是为了“显得高级”，而是为了把重复劳动变成稳定工作流。

原课用营销数据只是案例。你更应该学会的是背后的抽象：

- 不要把重复工作永远当成一次性任务
- 一旦流程开始重复，就该考虑结构化

## 给中文读者的实践建议

先别急着写 skill。

先观察你自己最近一周或一个月最常重复的 AI 使用场景，问自己三个问题：

- 我到底在反复让 AI 做什么
- 我每次重复说明的内容有哪些
- 哪些内容本来就可以提前写成固定规则

你会发现，很多“提示词工程”的本质，最后都会走向“技能化”。

## 常见误区

- 误区 1：只要任务复杂，就一定该做成 skill
- 误区 2：只要写了一次 prompt，就算有 workflow 了
- 误区 3：skill 是为了让 AI 变聪明，不是为了让流程更稳定

## 本章相关链接

- [初始对话 prompts](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L1-partI/prompts_initial_conversation.md)
- [课程示例 CSV](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L1-partI/campaign_data_week1.csv)
- [预算重分配规则](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L1-partI/budget_reallocation_rules.md)
- [示例 marketing skill 文件](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L1-partI/skill/analyzing-marketing-campaign/)
- [带 skill 的 prompts 版本](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L1-partI/prompts_with_skills.md)
- [课程演示生成的 Excel 报告](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L1-partI/output_report_example/Marketing_Campaign_Report_Dec9-15.xlsx)
- [Agent Skills adoption 研究页面](https://agentskills.io/home#adoption)
- [Agent Skills 官网](https://agentskills.io/home)
- [Anthropic 文档：Agent Skills Overview](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
- [Anthropic 博客：Introducing Agent Skills](https://claude.com/blog/skills)
- [Skilljar：Introduction to Agent Skills](https://anthropic.skilljar.com/introduction-to-agent-skills)

## 本章你应该带走什么

- skill 适合处理重复且结构稳定的工作流
- 它解决的不是“模型不会”，而是“每次都要重新解释”
- 真正值得做成 skill 的，是那些你已经在反复做的事情

## 本章练习

- 找一件你重复做过至少 3 次的 AI 任务，写出它的固定步骤
- 判断这件事更像“一次性提问”，还是“可沉淀的工作流”

## 这章学完后可以立刻做什么

- 从你最近的 AI 使用记录里挑 1 个高频任务
- 把它拆成“固定输入、固定步骤、固定输出”三部分

## 这章最适合用在哪些场景

- 你总觉得 AI“偶尔很好用，但不稳定”
- 你想把个人经验沉淀成可复用方法
- 你开始意识到团队里每个人都在重复写类似 prompt

## 建议产出

- 一份“候选 skill 清单”，至少列出 3 个你觉得未来值得沉淀的工作流
