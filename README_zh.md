# PDF EndNote IEEE Citation Renamer 技能

<p align="right"><a href="README.md">English</a> | <strong>简体中文</strong></p>

一个用于学术 PDF、EndNote 导入记录、IEEE 引文与系统化 PDF 重命名的元数据校核技能。

本仓库是该技能的 Git 源镜像。仓库文档保留在这里；精简的安装运行副本只应包含技能本身执行所需文件。

## 目录

- [用途](#用途)
- [仓库地图](#仓库地图)
- [如何使用](#如何使用)
- [核心契约](#核心契约)
- [资源索引](#资源索引)
- [验证命令](#验证命令)
- [维护说明](#维护说明)
- [语言一致性](#语言一致性)

## 用途

当任务与 [`SKILL.md`](SKILL.md) 中的描述匹配时使用该技能。先阅读 `SKILL.md`，再按照其中路由打开 references、scripts 或 assets。

主要能力：

- 从 PDF 和可用的可信外部记录中提取并校核书目信息。
- 基于已验证元数据生成 EndNote ENW 字段和 IEEE 风格引文字符串。
- 构建安全、确定性的 PDF 重命名方案，不静默覆盖原始文件。

## 仓库地图

| 路径 | 作用 |
|---|---|
| [`SKILL.md`](SKILL.md) | 入口、硬门、路由与验证说明 |
| [`README.md`](README.md) | 英文仓库导航 |
| [`README_zh.md`](README_zh.md) | 简体中文仓库导航 |

## 如何使用

1. 打开 [`SKILL.md`](SKILL.md)。
2. 按其中 reference routing 表只加载与任务相关的文件。
3. 对当前产物运行匹配的确定性辅助脚本或验证命令。
4. 在任何最终、就绪、发布、提交或完成声明前，若技能提供 final gates，必须先检查。

## 核心契约

- 不得编造 DOI、标题、作者、期刊/会议、年份、页码、arXiv ID 或 IEEE 字段。
- 发现元数据冲突时报告冲突，不静默选择其中一个记录。
- 在目标映射明确前，不进行破坏性重命名。

## 资源索引

当前没有 bundled reference、script 或 asset 目录。以 [`SKILL.md`](SKILL.md) 为准。

## 验证命令

根据变更文件运行匹配检查：

```bash
python path/to/quick_validate.py .
```

## 维护说明

- 保持 [`SKILL.md`](SKILL.md) 精简；如果技能包含 references，把细节路由到 references。
- 当 hard gates、references、scripts 或预期产物发生变化时，同步更新 README。
- 仅把仓库文档保留在该 Git 镜像中，不放入精简安装运行副本。
- 在同一提交中同步更新 [`README.md`](README.md) 与 [`README_zh.md`](README_zh.md)。

## 语言一致性

[`README.md`](README.md) 是本文档的英文对应版本。两份 README 应拥有相同章节、声明、质量门、命令与维护预期。

