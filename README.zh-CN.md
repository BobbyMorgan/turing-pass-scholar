# Turing-Pass Scholar

> **Built to pass a human editor, not an AI detector.**

[English](README.md) | [简体中文](README.zh-CN.md)

面向**英文原创研究论文和综述文章**的学术降 AI 工具，以一个可移植的 Agent Skill 同时支持 Claude Code 和 Codex。

## Before → After

**Before**

> Across the reviewed literature, AI has emerged as a pivotal and transformative force in precision medicine. First, image-classification models have been evaluated for diagnosis. Moreover, prediction models have been used to select treatments. Furthermore, multimodal systems combine imaging and clinical records. Taken together, these studies collectively underscore the immense potential of this rapidly evolving field.

**After**

> The reviewed studies evaluate AI for three precision-medicine tasks: image-based diagnosis, treatment selection, and the integration of imaging with clinical records.

证据没有变化；被删掉的是通用开场、堆叠连接词、重复总结和缺乏依据的拔高。

Turing-Pass Scholar 像一名挑剔的人类学术编辑一样阅读。它不猜测文稿由谁或什么工具写成，而是判断：学术读者是否会觉得这些文字套路化、空泛、判断失当、带有明显 AI 感，或者仅仅写得不好？只有存在真实写作问题时，它才介入。

**去掉 AI 感，保住科学内容。**

## 它为什么不同

### 依靠人的判断，而不是违禁词表

不统计所谓 AI 高频词，不机械制造句式变化，不输出 AI 概率，也不追求目标分数。常见模式只负责引导注意力，不直接构成判定。每项报告发现都必须指向一个读者能够感知的问题——即使完全不讨论文本来源，这个问题仍然值得作者修改。

### 敢于大修，也能精确保全

合适的干预可能是改一个短语、重构一个段落，也可能是建议整节重写。它不会用同义词替换掩盖结构问题；与此同时，数字、统计量、限定语、因果强度、术语、引文、交叉引用、数学内容、LaTeX、BibTeX 和作者立场都被视为不可随意移动的承重结构。

### 两种文体，两条阅读路径

- **原创研究论文：**更加宽容地处理第一人称、精确的术语重复、功能性枚举、高密度 Results 文本、技术性路标以及图表和章节引用。
- **综述文章：**重点审视空洞综合、通用分类框架、逐篇罗列、虚假共识、模糊归因和缺乏依据的全面性声称。

这不是笼统的“学术模式”，而是针对两种文体采用不同的容忍度和编辑注意力。

### 只报告值得行动的问题

报告不罗列已经通过的检查，不表扬正常写法，也不会为了显示工作量而强行修改。干净的文本只会收到简短的通过结论。降 AI 阅读过程中发现的实质性主张漂移、歧义、术语冲突和引文残留可以被顺带指出，但任务不会扩张成同行评审。

## 不只检查正文

引文和参考文献列表也会接受 AI 或草稿残留检查，包括提示词、私人备注、未解决的占位符、异常 DOI/URL 占位内容以及误入的中文全角标点。正常的文献管理器元数据受到保护；本工具不负责严格执行 APA、Vancouver 等特定格式。

支持完整手稿、单独章节和短片段。输入不完整时，它不会暗示自己审阅过没有看到的内容。

## 选择修改如何落地

1. **完整处理所提供的文本**——诊断并修改用户提供的全部内容，然后返回完整修改稿和简短的保全说明。
2. **逐段审批**——先返回编辑评估，只有经过用户确认后才讨论并落地受影响的段落。

如果文章类型或工作模式不明确，skill 会在开始编辑前一次性询问所有缺失选项。

## 安装

```bash
npx skills add BobbyMorgan/turing-pass-scholar
```

## 使用

```text
这是 original research paper 的 Discussion 片段。选择 B，只出报告，不要改写。
```

```text
This is a review article. Use whole-supplied-scope mode, preserve every citation,
and return the complete de-AI revision.
```

## 严格边界

Turing-Pass Scholar 仅支持英文原创研究论文和综述文章，其他学术文体和非学术写作均不处理。它不负责 AI 作者身份检测、翻译、外部事实核查、严格参考文献格式审查、抄袭检查，也不进行方法学、统计学、伦理或报告规范审查。表格仅供检查。

## 验证

v2.0.0 已在相互隔离的 Codex 会话中完成行为测试，去标识化测试材料涵盖生成式 AI 出现前的学术文本、模型生成的研究与综述文本、完整手稿与片段、两种审批模式、范围拒绝、引文残留、干净的 BibTeX 元数据、LaTeX 和科学内容保全案例。精简后的四重 gate 架构还接受了范围控制、结构诊断、引文残留和高密度研究文本误伤压力的回归测试。

测试有意不把文本来源当作真实标签：优质模型生成文本可以通过，较弱的人类写作也可能收到大幅修改意见。判断标准是每项发现对学术作者是否有用、是否经得起辩护。

## 致谢

由 [BobbyMorgan](https://github.com/BobbyMorgan) 创建。

AI 写作痕迹注意力指南部分改编自采用 MIT License 的 [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing)。对 [theclaymethod/unslop](https://github.com/theclaymethod/unslop) 的研究启发了本项目对上下文误判保护和内容保全机制的重视；本项目不包含 Unslop 的代码。

## 许可证

MIT，详见 [LICENSE](LICENSE)。
