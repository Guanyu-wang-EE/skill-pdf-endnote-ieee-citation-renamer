# PDF EndNote IEEE Citation Renamer 技能

<p align="right"><a href="README.md">English</a> | <strong>简体中文</strong></p>

一个用于学术 PDF、EndNote 导入记录、IEEE 引文与系统化 PDF 重命名的元数据校核技能。

本仓库是该技能的 Git 源镜像。仓库文档保留在这里；安装后的运行副本应保持精简，只包含执行所需文件。

## 功能范围

- 从 PDF 和可用的可信外部记录中提取并校核书目信息。
- 基于已验证元数据生成 EndNote ENW 字段和 IEEE 风格引文字符串。
- 构建安全、确定性的 PDF 重命名方案，不静默覆盖原始文件。

## 使用场景

当任务与 SKILL.md 中的描述匹配时使用该技能。先阅读 SKILL.md，再按照其中的路由表打开 references、scripts、assets 或索引资源。

典型使用场景：

- 从 PDF 文本和首页可见信息中提取候选元数据。
- 使用可用可信来源验证 DOI、标题、作者、期刊/会议、年份、页码与标识符。
- 输出 ENW 内容、IEEE 引文与重命名映射，并明确标注未解决冲突。

## 仓库内容

- `SKILL.md`

## 运行契约

- 不得编造 DOI、标题、作者、期刊/会议、年份、页码、arXiv ID 或 IEEE 字段。
- 发现元数据冲突时报告冲突，不静默选择其中一个记录。
- 在目标映射明确前，不进行破坏性重命名。

## 验证与复查

- 修改技能发现元数据前，先检查 SKILL.md frontmatter。
- 保持 Hard Gates、Reference Routing 与 Verification 和仓库实际文件一致。
- 如果存在 references/final-quality-gates.md，在任何最终、就绪、发布、提交或完成声明前使用它。
- 如果存在技能专用审计脚本，修改路由文件或确定性辅助程序后运行它。

## 维护说明

- 保持 SKILL.md 作为入口和路由器。
- 如果技能包含参考文件，将详细领域材料保存在 references/ 中。
- 将确定性辅助程序放在 scripts/ 或 tools/ 中，并在修改后验证。
- 同步更新 README.md 与 README_zh.md，确保两种语言描述相同的范围与质量门。
- 不要把仅属于仓库的文档移动到安装后的运行副本。

## 语言一致性

README.md 是本文档的英文对应版本。任一 README 变更时，应在同一个提交中同步更新另一种语言版本。
