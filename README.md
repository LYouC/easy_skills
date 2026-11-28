# Easy Skills

一套我日常使用的 AI 编码技能（Skills）集合。这里汇集了从优秀项目中学习、并结合自身实践打磨出来的技能，用于在 AI 编码工作流中复用稳定的做事方法。

## 目录结构

每个技能是一个独立文件夹，遵循 OpenCode Skill 规范：

```
easy_skills/
└── <skill-name>/
    ├── SKILL.md          # 技能主体：frontmatter(name/description) + 正文
    └── agents/
        └── openai.yaml   # 可选：显示名与简介
```

## 技能列表

| 技能 | 说明 |
| --- | --- |
| [`dev-wrap-up`](./dev-wrap-up/SKILL.md) | 开发收尾：开发结束后依次完成复盘、文档同步、提交。复盘总结「需求背景 / 实现方法 / 涉及模块 / 验证情况 / 风险遗留」；检查文档与实现是否一致并修正；按规范生成中文提交信息。支持显式触发与主动提醒。 |
| [`requirement-review`](./requirement-review/SKILL.md) | 需求体检：提出需求时，检查与现有实现/安排的关系（冲突 / 影响 / 契合 / 无关联），盘需求是否充分（按场景、输入、状态与流程发散边界情况并给补充建议），并确认 AI 是否真正理解（先带选项提问、无疑问后再输出理解说明）。按复杂度分简单/分析两档自适应；仅手动触发。 |

## 使用方式

- **项目内使用**：将这些技能文件夹放入项目的技能目录，或按 OpenCode 的 Skill 加载规则放置。
- **全局使用**：把技能文件夹复制到 `~/.config/opencode/skills/` 下即可被全局加载。
- **互相引用**：技能可被其他技能按名字直接引用（例如「开发完成后调用 `dev-wrap-up`」）。

## 新增技能约定

1. 一个技能一个文件夹，文件夹名即技能 `name`（英文 slug）。
2. `SKILL.md` 顶部使用 YAML frontmatter，包含 `name` 与 `description`；`description` 写清触发条件。
3. 正文保持可执行：说明「何时触发 / 做什么 / 判断规则 / 边界与安全」。
4. 可选的 `agents/openai.yaml` 提供显示名与简介。
