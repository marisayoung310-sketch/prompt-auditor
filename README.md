# Prompt Auditor

一个零 API 成本的 Codex Skill，用于分析、评分和优化不同类型的 Prompt，并生成结构化评审报告。

它支持写作、研究、编程、数据分析、图片与视频生成、Agent 和 System Prompt，也支持批量比较。报告包含多维评分、优先级问题、可直接复制的优化版本和修改说明。

## 能力

- 识别 Prompt 类型和目标
- 按 7 个通用维度进行 100 分制评审
- 对代码、研究、视觉生成和 Agent Prompt 应用专项检查
- 分析单条或批量 Prompt
- 保留原始意图，不擅自补造业务需求
- 输出完整报告或快速报告
- 无 API、数据库、服务器或模型部署要求

## 安装

```bash
git clone https://github.com/marisayoung310-sketch/prompt-auditor.git ~/.codex/skills/prompt-auditor
```

重新打开 Codex 任务后，Skill 会出现在可用 Skills 中。

## 使用

完整评审：

```text
使用 $prompt-auditor 分析下面的 Prompt，生成完整报告：

帮我写一份产品方案。
```

批量比较：

```text
使用 $prompt-auditor 比较以下 Prompt，生成评分表并分别给出优化版本：

P1：帮我写一份产品方案。
P2：你是一名产品经理，请为大学生 AI 学习助手撰写产品方案。
```

快速评审：

```text
使用 $prompt-auditor 快速检查这条图片生成 Prompt，并给我一个优化版本。
```

## 报告结构

完整报告默认包含：

1. 一句话结论
2. 多维评分表
3. 按影响排序的问题
4. 优化后的完整 Prompt
5. 修改说明
6. 必要的待确认问题

评分用于诊断和比较，不代表更高分一定产生更好的模型输出。

## 方法来源

本项目参考了清华大学 THUDM [AlignBench](https://github.com/THUDM/AlignBench) 的多维度、规则校准和可解释评测思想，并将其重新设计为 Prompt 输入质量评审体系。

Prompt Auditor 不是 THUDM 官方项目，也不是 AlignBench 的复现或分支。AlignBench 评估模型回答，本项目评估执行前的 Prompt；评分维度与 Skill 实现均为原创设计。详细说明见 [methodology.md](references/methodology.md)。

## 项目结构

```text
prompt-auditor/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── methodology.md
    └── report-spec.md
```

## License

MIT
