# Agent Skills 中文课

> 一套把英文课程《Agent Skills with Anthropic》重写为中文学习路径的 GitHub 文档课程。

![status](https://img.shields.io/badge/status-ready_for_first_release-2ea44f)
![audience](https://img.shields.io/badge/audience-中文零基础%20%2F%20弱英文用户-0969da)
![format](https://img.shields.io/badge/format-markdown_course-8250df)

这不是逐字翻译稿，也不是课程字幕搬运仓库。

它更像一套面向中文用户重新编排的学习版课程：

- 保留原课程主线和核心知识结构
- 用更自然的中文教学表达重写内容
- 补充术语解释、背景知识和阅读导航
- 按适合 GitHub 阅读与分享的方式组织仓库

## 为什么做这个仓库

原课程内容很好，但对很多中文读者来说，真正的门槛往往不是“学不会”，而是：

- 英文理解成本高
- 产品名词太密
- 工程上下文默认太多
- 视频课逻辑不适合反复查阅

这个仓库想做的，不是把原课“翻成中文”就结束，而是把它整理成一套更适合中文读者反复查阅、反复练习、逐步上手的文档课程。

## 这套课适合谁

- 想学 `Agent`、`Skill`、`MCP`，但读英文资料比较吃力的人
- 已经在用 AI 助手，但还说不清 `Skill` 到底解决什么问题的人
- 想把零散 prompt 变成稳定工作流的人
- 想理解 `Claude Code`、`Claude API`、`Agent SDK` 中 skills 用法的人

## 学完后你会更清楚什么

- 什么是 `Agent Skills`
- 为什么它不只是“高级一点的 prompt”
- `Skill`、`Tool`、`MCP`、`Subagent` 分别负责什么
- 一个标准 skill 至少该怎么组织
- 在 `Claude.ai`、`Claude API`、`Claude Code`、`Agent SDK` 中，skills 的角色有什么不同
- 如何把一套重复工作整理成可复用的 skill

## 推荐阅读顺序

1. [00 课程导读](lessons/00-课程导读.md)
2. [01 为什么要把重复工作做成 Skill](lessons/01-为什么要把重复工作做成-skill.md)
3. [02 什么是 Agent Skills 与开放标准](lessons/02-什么是-agent-skills-与开放标准.md)
4. [03 Skills、Tools、MCP、Subagents 怎么分工](lessons/03-skills-tools-mcp-subagents-怎么分工.md)
5. [04 认识官方预置 Skills](lessons/04-认识官方预置-skills.md)
6. [05 如何创建自定义 Skills](lessons/05-如何创建自定义-skills.md)
7. [06 在 Claude API 中使用 Skills](lessons/06-在-claude-api-中使用-skills.md)
8. [07 在 Claude Code 中使用 Skills](lessons/07-在-claude-code-中使用-skills.md)
9. [08 在 Agent SDK 中使用 Skills](lessons/08-在-agent-sdk-中使用-skills.md)
10. [09 结课总结与下一步](lessons/09-结课总结与下一步.md)

## 如果你时间不多，可以这样读

- 只想快速理解概念边界：读 [02](lessons/02-什么是-agent-skills-与开放标准.md) + [03](lessons/03-skills-tools-mcp-subagents-怎么分工.md)
- 只想知道 skill 怎么写：读 [05](lessons/05-如何创建自定义-skills.md)
- 你是开发者：重点读 [06](lessons/06-在-claude-api-中使用-skills.md)、[07](lessons/07-在-claude-code-中使用-skills.md)、[08](lessons/08-在-agent-sdk-中使用-skills.md)
- 想先扫清术语障碍：读 [术语表](resources/glossary.md) 和 [FAQ](resources/faq.md)

## 仓库结构

```text
agent-skills-course-zh/
├── README.md
├── NOTICE.md
├── LICENSE
├── CONTRIBUTING.md
├── GITHUB_LAUNCH.md
├── RELEASE_CHECKLIST.md
├── lessons/
├── resources/
│   ├── course-map.md
│   ├── glossary.md
│   ├── faq.md
│   ├── references.md
└── assets/
```

## 仓库里最值得先看的文件

- [lessons](lessons)：中文课程正文，建议按顺序读
- [resources/glossary.md](resources/glossary.md)：第一次遇到术语卡住时，先看这里
- [resources/faq.md](resources/faq.md)：适合零基础读者补概念边界
- [resources/course-map.md](resources/course-map.md)：适合对照原课时使用
- [resources/references.md](resources/references.md)：适合学完一遍后继续往下延伸
- [NOTICE.md](NOTICE.md)：发布说明与边界提醒
- [LICENSE](LICENSE)：当前仓库的授权说明
- [CONTRIBUTING.md](CONTRIBUTING.md)：贡献建议
- [GITHUB_LAUNCH.md](GITHUB_LAUNCH.md)：GitHub 首发说明、仓库简介和首发文案建议
- [RELEASE_CHECKLIST.md](RELEASE_CHECKLIST.md)：首发前检查清单

## 这套整理版和原课是什么关系

- 原课主题：`Agent Skills with Anthropic`
- 本仓库定位：中文学习版 / GitHub 阅读版 / 零基础友好版
- 处理方式：保留知识结构，重写中文讲法，补术语解释和中文语境说明
- 发布策略：公开仓库中不再保留原始英文材料副本，只保留章节映射与中文整理内容

## 如果你准备公开发布，先确认这几件事

这个仓库虽然已经整理成适合公开发布的结构，但它仍然涉及基于第三方课程资料进行的学习性改写。

正式公开前，建议你至少确认下面几件事：

- 你是否接受当前 `LICENSE` 对第三方材料的排除条款
- 你是否需要再补充更明确的出处说明或引用说明

相关说明见：

- [NOTICE.md](NOTICE.md)
- [LICENSE](LICENSE)
- [RELEASE_CHECKLIST.md](RELEASE_CHECKLIST.md)

## 当前完成度

- [x] 中文课程首页
- [x] 10 章中文正文
- [x] 术语表、FAQ、课程映射
- [x] 原课章节映射与出处整理
- [x] 开源发布辅助文件
- [x] 首发前结构自检

## 如果你要继续打磨，建议按这个顺序处理

如果你准备继续推进公开发布，建议按这个顺序处理：

1. 再通读一遍每章正文，确认有没有你自己的表达习惯需要替换
2. 根据你的发布策略确认 `LICENSE` 和 `NOTICE` 文案
3. 补一个封面图或社交分享图到 `assets/`
4. 再做第一次 Git 提交

## 最后说明

- 本仓库以学习整理和中文传播为目的
- 不保证覆盖原课程所有演示细节
- 原课程中的链接、价格、产品界面和能力范围后续可能发生变化
- 涉及官方产品能力时，请以官方最新文档为准
