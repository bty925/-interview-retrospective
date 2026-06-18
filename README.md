# interview-retrospective · 面试复盘技能

> A Claude [Agent Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) that turns a raw interview (transcript + job description) into a coach-grade retrospective — decoding what each question was *really* testing, diagnosing your recurring patterns, and producing a targeted drill plan for your next round.
>
> 一个 Claude [Agent Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview):把一场原始面试(转写稿 + JD)变成教练级复盘——解码每道题真正在考什么、诊断你反复出现的问题模式、并给出下一场的针对性练习计划。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

---

## English

### What it does

After any interview, give Claude your transcript (or recording notes) plus the job description, and this skill produces:

1. **A conversational analysis** — question by question, it names the *dimension* each question was testing, the interviewer's *subtext* and likely follow-up, and a concrete *model answer* that would score.
2. **A downloadable Word document** — the full retrospective, formatted and ready to keep.
3. **A running profile** — a living dashboard of your recurring patterns that carries forward across interviews, so each retrospective gets sharper over time.

### The method, in one line

Interviewers test **capabilities**, not answers. Most candidates lose points not because the content is wrong (the "engine") but because of delivery (the "transmission"). This skill diagnoses the transmission layer and fixes it.

It ships with three analytical tools:
- **Five testing dimensions** — depth check, prioritization, metacognition, and two kinds of epistemics — each with signal words and how to score.
- **The abstraction ladder** — the predictable order interviewers climb, so you can pre-load your next answer.
- **A three-layer problem model** — structure / commitment / granularity, used to track recurring weaknesses.

### Install

**Claude Code** — skills live as folders:
```bash
# personal (global)
cp -r interview-retrospective ~/.claude/skills/
# or project-scoped
cp -r interview-retrospective <your-project>/.claude/skills/
```
Make sure the path is `~/.claude/skills/interview-retrospective/SKILL.md` (no extra nesting), then restart Claude Code.

**Claude.ai / desktop app** — zip the `interview-retrospective` folder into a `.skill` file (or download a release) and upload it in Settings → Capabilities → Skills.

### Use

Say "帮我复盘" / "review my interview", or just paste a transcript with the JD. For cross-interview tracking, also share your latest profile doc each time. Optional dependency for the document generator: `pip install python-docx`.

### Privacy note

The bundled `assets/profile-seed.md` is a **fictional example**. Your real profile (with actual companies and interview details) stays on your machine — don't commit it to a public repo.

---

## 中文

### 它能做什么

任何一场面试后,把转写稿(或录音纪要)加上岗位 JD 发给 Claude,这个技能会产出:

1. **对话里的分析** — 逐题告诉你每道题在考哪个*维度*、面试官的*潜台词*和大概率的追问、以及一个能得分的具体*示范答法*。
2. **一份可下载的 Word 文档** — 完整复盘,排好版,留着随时看。
3. **一份滚动个人档案** — 一块记录你反复出现问题的活看板,跨场累积,让每次复盘越来越准。

### 方法,一句话

面试官考的是**能力**,不是答案。多数人失分不是因为内容错(「发动机」),而是因为表达(「传动」)。这个技能专门诊断并修复传动层。

内置三件分析工具:
- **五个考察维度** — 深度核实、权衡判断、超越/元认知、以及两种认识论 — 每个都配信号词和答题落点。
- **抽象阶梯** — 面试官层层往上爬的可预测顺序,让你预加载下一题的答案。
- **三层问题模型** — 表达结构 / 判断承接 / 内容深度,用来追踪反复出现的弱点。

### 安装

**Claude Code** — skill 以文件夹形式安装:
```bash
# 个人全局
cp -r interview-retrospective ~/.claude/skills/
# 或仅在某个项目
cp -r interview-retrospective <你的项目>/.claude/skills/
```
确认路径是 `~/.claude/skills/interview-retrospective/SKILL.md` 这一层(别多套文件夹),然后重开 Claude Code。

**Claude.ai / 桌面 App** — 把 `interview-retrospective` 文件夹打包成 `.skill`(或下载 release),在 设置 → Capabilities → Skills 里上传。

### 使用

说一句「帮我复盘」,或直接把转写稿和 JD 一起粘贴进来。想跨场追踪进步,每次再附上你最新的档案文档。文档生成器的可选依赖:`pip install python-docx`。

### 隐私提示

仓库里的 `assets/profile-seed.md` 是一份**虚构示例**。你的真实档案(含真实公司和面试细节)请只留在本地——别提交到公开仓库。

---

## Structure

```
interview-retrospective/
├── SKILL.md                      # 主流程 main workflow
├── references/
│   ├── decode-framework.md       # 五维 + 抽象阶梯 + 三层模型
│   ├── feedback-method.md        # 教练级反馈写法 + 起手式
│   └── output-templates.md       # docx 样式规范 + 生成器用法
├── scripts/
│   └── make_docx.py              # JSON → 排版 .docx 生成器
└── assets/
    └── profile-seed.md           # 档案种子(示例)
```

## License

[MIT](./LICENSE) — use it, change it, ship it; just keep the copyright notice.

## Acknowledgements

Built collaboratively with Claude. The methodology was distilled from real interview-coaching sessions.
