# Turing-Pass Scholar

[English](README.md) | [简体中文](README.zh-CN.md)

面向**英文原创研究论文与综述文章**的学术降 AI 写作工具，以一个可移植的 Agent Skill 同时支持 Claude Code 和 Codex。

Turing-Pass Scholar 以具备学术素养和独立判断的读者身份工作。它不猜测文稿由谁或什么工具撰写，而是追问一个更有用的问题：学术读者是否会觉得这些文字套路化、空泛、判断失当、带有明显 AI 感，或者仅仅写得不好？

**当前版本：v1.0.0**

## 功能

- 在问题实际存在的尺度上诊断 AI 写作痕迹，包括短语、句子、段落、章节和论述结构。
- 保全数字、单位、统计量、公式、术语、否定、限定语、因果强度、引文、交叉引用和作者立场。
- 分别处理原创研究论文与综述文章。研究论文对第一人称、必要的术语重复、功能性列举、高密度 Results 文本以及图表和章节引用更加宽容；综述文章则重点审视空洞综合、通用分类框架、逐篇罗列、虚假共识和缺乏依据的全面性声称。
- 支持完整手稿、单独章节和短片段，不会暗示自己审阅过用户没有提供的部分。
- 可以顺带指出降 AI 阅读过程中发现的实质性主张漂移、歧义、术语冲突或章节功能问题，但不会扩张成同行评审。
- 排查引文与参考文献条目中的 AI 或草稿残留，例如提示词、私人备注、占位符、异常 DOI/URL 占位内容和误入的中文全角标点；不负责严格执行 APA、Vancouver 等特定格式。
- 保护 LaTeX 命令、标签、引文键、数学内容、BibTeX 结构和正常的文献管理器元数据。

## 两种工作模式

编辑前，skill 会先确认一种工作模式：

1. **完整处理所提供的文本**——诊断并修改用户提供的全部内容，然后返回完整修改稿和保全说明。
2. **逐段审批**——先返回评估并停止，只有在用户批准后才修改受影响的段落。

如果文章类型或工作模式不明确，skill 会一次性询问所有缺失选项。Letter、short communication、correspondence、editorial、perspective、commentary、case report、protocol、学位论文、基金申请、课程作业、审稿意见以及非学术写作均明确不在范围内。

## 与普通 humanizer 的区别

多数 humanizer 追求泛化的自然感或个人化表达。Turing-Pass Scholar 保持学术语体，并将技术精确性视为不可随意改动的承重结构。模式匹配只负责引导注意力，不直接构成判定。每项报告发现必须指出一个即使不谈 AI 来源也值得修改、且读者能够感知的问题；否则不写入报告。

报告只呈现有效发现，不罗列已经通过的检查，不解释正常写法为何合理，不生成 AI 概率，也不填充空栏目。对于没有值得报告问题的片段，只会给出简短的通过结论。

## 安装

Windows、macOS、Linux，以及个人级和项目级安装方式见 [INSTALL.md](INSTALL.md)。其中的路径与调用方式遵循当前的 [Claude Code Skills 文档](https://code.claude.com/docs/en/skills)和 [OpenAI Skills 文档](https://developers.openai.com/codex/skills)。

常用路径：

| 工具 | 个人 skill 目录 | 显式调用 |
| --- | --- | --- |
| Claude Code | `~/.claude/skills/academic-deslop/` | `/academic-deslop` |
| Codex | `$HOME/.agents/skills/academic-deslop/` | `$academic-deslop` |

同一个 `academic-deslop` 文件夹可同时用于两个工具。无需脚本、Python 包、网络访问、外部检测器或 API key。

## 使用示例

```text
这是 original research paper 的 Discussion 片段。选择 B，只出报告，不要改写。
```

```text
This is a review article. Use whole-supplied-scope mode, preserve every citation, and return the complete de-AI revision.
```

```text
这是 research paper 的 LaTeX 稿。选择 A；顺带检查 BibTeX 条目里有没有提示词、私人备注或中文全角标点。
```

## 范围与非目标

Turing-Pass Scholar 仅支持英文原创研究论文和综述文章。它不负责 AI 作者身份检测、翻译、外部事实核查、严格的参考文献格式审查、抄袭检测、方法学/统计学/伦理审查、报告规范检查、期刊选择，也不会虚构缺失的学术内容。

表格仅供检查，不改写数值和单元格。更广义的学术编辑观察默认只作为建议，除非用户另行授权实质性编辑。

## 验证

v1.0.0 已在相互隔离的 Codex 会话中完成行为测试，去标识化测试片段涵盖：

- 生成式 AI 出现前公开授权的原创研究与综述文本；
- 未刻意植入错误的模型生成研究与综述文本；
- 完整处理、逐段审批、片段输入、范围拒绝以及模式缺失时的交互；
- 引文残留、干净的 BibTeX 文献库元数据、LaTeX 保全，以及数字、单位、统计量、否定、限定语、图表引用和引文键。

评估有意采用定性标准，不把文本来源当作真实标签：优质模型生成文本可以通过，人类写作也可能收到强烈的编辑意见。验收标准是相关发现对学术作者是否有用、是否经得起辩护。

## 致谢

由 [BobbyMorgan](https://github.com/BobbyMorgan) 创建。

AI 写作痕迹注意力指南部分改编自采用 MIT License 的 [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing)。对 [theclaymethod/unslop](https://github.com/theclaymethod/unslop) 的研究启发了本项目对上下文误判保护和内容保全机制的重视；本项目不包含 Unslop 的代码。

## 许可证

MIT，详见 [LICENSE](LICENSE)。
