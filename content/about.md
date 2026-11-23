---
title: 关于 DroidNote
type: about
---

**DroidNote** 是一个面向安卓手机日常使用与长期维护的个人知识库，旨在把零散的折腾经验、系统设置要点、命令行速查和排障步骤沉淀为结构化手册。

## 编写原则

- **可执行优先**：优先给出具体设置路径、CLI 命令与验证方式，避免空泛描述。
- **安全与可逆**：涉及停用系统组件、ADB 调试、Fastboot 或 Root 操作时，明确列出前置条件、风险与回滚方法。
- **先免 Root 后进阶**：能通过原生设置或 Shizuku / ADB 解决的问题，不强求解锁 Bootloader 或获取 Root 权限。

## 技术栈

- 文档框架：[Hugo](https://gohugo.io/) + [Hextra](https://imfing.github.io/hextra)
- 自动构建与托管：GitHub Actions + GitHub Pages