# Writer: Stages & Schemas

Outline 与 Draft 两阶段的输入、产出与验收标准。执行步骤见 `prompts/`，文风与质检见 `references/voice.md`、`references/writing-qc.md`。

## Stage 1: Outline

从素材中提炼**唯一核心主张**，锁定读者与结构，防止草稿跑偏。

### 输入

- 原始素材（纪要 / 文章 / 播客字幕 / brief / 灵感）
- 可选：`sc-content-mining` 选题清单（衔接方式见 [content-mining.md](content-mining.md)）
- 可选参数：`--angle`（角度倾向）、`--length`（short / medium / long）

### outline.md Schema

| 字段 | 说明 | 必填 |
|------|------|------|
| **Angle** | 一句话切入角度（有 `--angle` 时须吸收） | ✅ |
| **Reader** | 读者是谁 + 当前信念 + 看完收获（一句话，越具体越好） | ✅ |
| **Core claim** | 全文唯一论点，偏反共识、可点名、在作者权限内 | ✅ |
| **Counter-view** | 最强反方一句话；写不出 = 主张太弱，回退重选 | ✅ |
| **Structure** | Body 结构类型（见 wechat-style / xhs-style）+ 一句理由 | ✅ |
| **Sections** | 4–8 节：标题 + 1–3 bullets（各自锚到来源） | ✅ |
| **Hook** | 开头段草稿（公众号 ≤80 字 / 小红书封面 ≤15 字） | ✅ |
| **CTA** | 结尾一个具体问题或下一步 | ✅ |
| **Source map** | claim ↔ 来源文件/锚点；无源标 `[opinion: author]` 或删除 | ✅ |
| **Voice notes** | 可选：本文口吻要点（见 voice.md） | 可选 |

### 验收

- 只有一个 Core claim
- Reader 可指认到具体人群
- Counter-view 真实可信，不是稻草人
- 每条事实主张能回溯到 Source map
- 素材过薄时**停下来要材料**，不编造主张

## Stage 2: Draft

将 outline 扩成可发布正文（及小红书图片规格）。

### 输入

- 已确认的 `outline.md`
- 平台 style：`wechat-style.md` 或 `xhs-style.md`
- 口吻：`voice.md`（含 EXTEND.md 用户口吻覆盖）
- 检查：`writing-qc.md`

### draft 产出

| 平台 | 产出 |
|------|------|
| wechat | `title`（H1）+ Hook + 各节正文 + 收尾 CTA + `## 参考链接` |
| xhs | 标题 + caption + 图片系列规格（handover 见 `xhs-to-images-handover.md`）+ 标签 |

### 验收

- Outline 的 Reader / Core claim / Counter-view 三者均被正文覆盖
- 反方在正文中被认真回应一段（不是一句敷衍）
- 段落、字数、CTA 符合平台 style
- 已跑完 `writing-qc.md` 四层自检并输出质检报告
- 无编造经历、无无源数据、无空泛工具名

## 与其他 skill 的边界

| 阶段 | 负责 | 不负责 |
|------|------|--------|
| 选题挖掘 | `sc-content-mining` | 成文 |
| 大纲 + 草稿 | `sc-writer`（本 skill） | 事实合规、链接健康 |
| 写作质检 | 本 skill `writing-qc.md` | 平台红线 / fact-check |
| 发布前审计 | `sc-content-review` | 文风、结构、节奏 |
| 发布 | `sc-publish-wechat` / `sc-publish-xhs` | — |
