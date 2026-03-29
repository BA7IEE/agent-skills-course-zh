# 04 认识官方预置 Skills

## 这章讲什么

这一章带你看一个很重要的现实问题：

> 如果已经有现成的技能可以用，我们是不是没必要每次都从零开始写？

原课展示了 Anthropic 提供的一些预置 skills，比如：

- [Excel / xlsx](https://github.com/anthropics/skills/tree/main/skills/xlsx)
- [PowerPoint / pptx](https://github.com/anthropics/skills/tree/main/skills/pptx)
- [Word / docx](https://github.com/anthropics/skills/tree/main/skills/docx)
- [PDF](https://github.com/anthropics/skills/tree/main/skills/pdf)
- [skill-creator](https://github.com/anthropics/skills/tree/main/skills/skill-creator)

如果你想直接看官方 skills 总列表，可以从这里进入：

- [Anthropic skills 列表](https://github.com/anthropics/skills/tree/main/skills)

这里有一个很容易被忽略、但其实很重要的细节：

- Word、PDF、PowerPoint、Excel 这类属于 document skills
- 它们在 Claude.ai 里是内建能力，不属于普通的可选样例
- 另外还有一批 example skills，可以按需开启或关闭
- `skill-creator` 则是默认开启的示例 skill 之一

## 这一章建议怎么读

不要带着“我要不要马上照抄这些 skill”去读。

更好的读法是：

- 先看它们是怎么组织的
- 再看它们为什么这样组织
- 最后再想哪些部分适合迁移到你自己的场景里

## 这里第一次出现的词先解释一下

- `预置 skill`：平台官方已经准备好的 skill
- `skill-creator`：一个专门帮助你创建、检查和整理 skill 的 skill

## 为什么先看预置 skills 很重要

很多人学 skill 时，第一反应就是“我要自己写一个”。

但更实际的顺序往往是：

1. 先看别人是怎么组织 skill 的
2. 再看预置 skill 都解决了哪些典型问题
3. 最后再决定自己要不要从零写，还是在现有结构上改

这跟学写代码很像。你通常不是从发明编程语言开始，而是先看成熟项目怎么组织。

## 这一章主要看什么

原课重点做了几件事：

- 看官方仓库里的 skills 列表
- 分析一个 skill 的目录结构
- 理解预置 skill 的说明、要求、设计原则
- 演示如何把多个能力串成一个完整工作流

这里最值得学的，不只是“它们有哪些”，而是“它们是怎么写成可复用工作流的”。

## 预置 skill 给你的启发

好的预置 skill 一般都有这些特点：

- 任务边界清楚
- 输入输出预期明确
- 遇到不同情况有处理规则
- 会引用脚本、模板和附加文件
- 不会把所有内容一股脑塞进主文件里

也就是说，成熟 skill 的重点从来不是“写得长”，而是“写得有结构”。

## 原课案例里的关键认识

原课展示了把营销分析 skill 和其他能力拼成完整工作流的过程，比如：

- 先通过 MCP 接入 BigQuery 这类外部数据源
- 再根据品牌规范生成输出
- 最后把结果整理成表格或演示文稿

这说明 skill 的价值不只在“单点任务”，而在于它能成为整个工作流里的方法层。

## 中文场景例子

你可以把预置 skill 想成“平台已经帮你写好的成熟模板”。

就像很多中文团队会先拿一个成熟周报模板来改，而不是从白纸开始写。预置 skill 的价值，往往也是先给你一个已经被验证过的起点。

## 这一章最该建立的习惯

以后你看到一个好用的 skill，不要只问：

- 它能不能直接拿来用

还要问：

- 它为什么会被写成这样
- 哪一部分是通用方法
- 哪一部分是特定场景资源
- 哪一部分是以后可以抽出来复用的

## 如果你现在就想上手，建议这样做

不要一上来就自创复杂 skill。

先做两件事：

1. 挑一个成熟预置 skill，拆解它的目录和 [`SKILL.md`](../resources/examples/skill-template/SKILL.md)
2. 用你自己的话复述：这个 skill 解决什么问题、什么时候触发、有哪些资源依赖

只要你能复述清楚，你就已经开始真正理解 skill 设计了。

## 常见误区

- 误区 1：预置 skill 能直接覆盖所有自己的工作场景
- 误区 2：只看功能，不看它的组织方式
- 误区 3：觉得“官方做的”就一定不需要改

## 本章相关链接

- [Anthropic skills 总列表](https://github.com/anthropics/skills/tree/main/skills)
- [pptx skill](https://github.com/anthropics/skills/tree/main/skills/pptx)
- [skill-creator](https://github.com/anthropics/skills/tree/main/skills/skill-creator)
- [Part 1 prompts](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/prompts.md#part-1-updating-the-marketing-skill)
- [更新后的 marketing skill 文件](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/updated_marketing_skill/analyzing-marketing-campaign/)
- [课程示例 CSV](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/campaign_performance_4weeks.csv)
- [SQLite MCP server](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/sqlite)
- [BigQuery 配置说明](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/additional_references/table_setup.md#bigquery-setup)
- [SQLite 配置说明](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/additional_references/table_setup.md#sqlite-setup)
- [品牌规范文件](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/brand_guidelines_files/)
- [Part 2 prompts](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/prompts.md#part-2--creating-the-brand-guideline-skill)
- [课程拍摄中生成的品牌 skill 文件](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/brand_guidelines_skill/craftedwell-brand/)
- [Part 3 prompts](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/prompts.md#part-3-implementing-the-entire-workflow)
- [课程拍摄中生成的 Slides 示例](https://github.com/https-deeplearning-ai/sc-agent-skills-files/tree/main/L3/output_report_example/CraftedWell_Weekly_Report_Dec16-22.pptx)

## 本章你应该带走什么

- 预置 skills 是最好的学习样本之一
- 你应该学习它们的结构和方法，而不只是功能列表
- 成熟的 skill 通常代表一套经过实践打磨的工作流表达方式

## 本章练习

- 随便选一个预置 skill，用三句话写清楚它解决什么问题、什么时候用、依赖什么资源
- 判断它哪些部分是“方法”，哪些部分是“素材”

## 这章学完后可以立刻做什么

- 挑一个你最感兴趣的预置 skill，拆一遍它的目录和入口逻辑
- 用你自己的场景判断它是否值得改造成中文版或私有版

## 这章最适合用在哪些场景

- 你准备模仿成熟 skill 的组织方式
- 你不想从零写，想先看别人的样板
- 你想找一个最适合自己上手的切入口

## 建议产出

- 一页“预置 skill 拆解笔记”，记录它的用途、结构和你可借鉴的点
