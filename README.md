# Make It Click（一点通）

**不把知识讲浅，而是换个角度，一点就通。**

Make It Click 是一个跨 AI 使用的解释型 Skill。它不会把所有问题强行改写成比喻，也不会削减原答案的知识、推理和专业内容；它只针对用户不理解的地方，选择当下最贴切、易懂、准确的表达方式。

```text
使用 $make-it-click，从空间立体几何的角度讲讲高等代数中求解线性和非线性方程组。
```

## 它解决什么问题

同一个概念可以用白话、例子、类比、反例、几何视角、逐步推演或对比来解释。问题不在于哪一种方式最常用，而在于哪一种最适合当前知识点和用户真正卡住的位置。

Make It Click 会：

- 先识别用户不理解的概念、关系或步骤；
- 用户指定视角时，优先判断它是否准确、适合；
- 用户没有指定时，从统一表达库中选择最优方法；
- 必要时组合少量方法，或创造库中没有的新方法；
- 保留证明、推导、算法、代码逻辑、例外条件和专业术语；
- 从直观理解自然回到正式定义和专业表达。

选择标准不是随机、热度或使用频率，而是：

1. 科学准确；
2. 贴合当前疑问；
3. 容易理解；
4. 内容足够完整；
5. 表达自然通顺。

准确性是硬边界。如果类比反而会误导，直接用白话或具体例子会更好。

## 一个统一的表达库

[`expression-library.md`](skill/make-it-click/references/expression-library.md) 是项目唯一的公共表达库，包含两类条目：

- **表达方法**：具体怎么讲，例如白话、完整类比、几何视角、反例和逐步因果链；
- **表达框架或范式**：面对不同性质的内容，怎样选择和组合表达方法。

每个条目都记录适用情况、不适用情况、使用方式、组合方式、有效原因、回到专业表达的路径、示例和准确性边界。这个内部结构不会强迫最终回答使用固定格式。

如果用户或 AI 实际使用了库中没有的新方法或框架，AI 会先完成解释，再询问用户是否将它整理为公共库贡献候选。仅仅更换措辞、数字或例题，不算新方法。

## 使用方式

本 Skill 只能显式调用，而且每次调用只影响当前回答。

### Codex

将 [`skill/make-it-click`](skill/make-it-click) 复制到：

```text
$CODEX_HOME/skills/make-it-click
```

重新加载 Skill 后，使用 `$make-it-click` 调用。

### Claude Code

Claude Code 支持 `SKILL.md`。将同一目录复制到个人或项目 Skill 目录，例如：

```text
~/.claude/skills/make-it-click/
```

然后显式调用该 Skill。`SKILL.md` 中的描述也要求它不能自动接管普通回答。

### 其他 AI 或 Agent

对于不支持文件式 Skill 的产品，将 `SKILL.md` 作为当前请求的 system 或 developer 指令，并按需提供表达库。详细加载顺序见 [`adapters/generic-agent/INSTRUCTIONS.md`](adapters/generic-agent/INSTRUCTIONS.md)。

## 示例

适合的调用包括：

```text
使用 $make-it-click，帮我讲清楚这道算法题为什么要用动态规划。
```

```text
使用 $make-it-click，SEO、GEO 分别是什么意思？它们有什么区别？
```

```text
使用 $make-it-click，你说这个页面“AI 味很重”，具体是哪些地方造成的？
```

用户指定的方法不是凌驾于准确性之上的命令。如果指定视角会产生错误认识，AI 应说明问题，修正该视角或换用更合适的方法。

## 仓库结构

```text
.
├── adapters/
│   └── generic-agent/
│       └── INSTRUCTIONS.md
├── evals/
│   └── cases.md
├── skill/
│   └── make-it-click/
│       ├── SKILL.md
│       ├── agents/
│       │   └── openai.yaml
│       └── references/
│           ├── contributing.md
│           └── expression-library.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

核心规则只在 `SKILL.md` 中维护。通用适配器只说明怎样加载，不复制核心方法。表达方式和选择范式全部维护在同一个公共库中。

## 贡献新方法或框架

没有仓库写入权限的普通用户也可以贡献：AI 会在得到用户同意后生成规范候选，由用户提交到公共仓库。仓库维护者审核并合并后，条目才真正进入公共库。

贡献要求见 [`CONTRIBUTING.md`](CONTRIBUTING.md)。不要提交整段私人对话；应提炼可以跨问题复用的方法，并明确它的准确性边界。

## 验收

运行官方 Skill 结构检查：

```powershell
python -X utf8 "$env:CODEX_HOME\skills\.system\skill-creator\scripts\quick_validate.py" "skill\make-it-click"
```

再使用 [`evals/cases.md`](evals/cases.md) 做行为验收。测试重点是选型、准确性、内容保留、创新识别和显式调用边界，不匹配固定措辞。

## License

[MIT](LICENSE)
