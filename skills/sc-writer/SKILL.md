---
name: sc-writer
description: 两阶段内容创作（大纲→草稿），支持微信公众号（wechat）和小红书（xhs）两个平台。将原始素材转为平台适配内容，并套用作者口吻规格、完成四层写作质检。触发词包括但不限于：写大纲、拟提纲、写初稿、写文章、写稿子、帮我写、续写、扩写、写小红书文案、写公众号文章、用我的风格写、把这份材料写成文章。丢来 PDF/纪要/brief/语音转文字说「帮我写」也应触发。不收集素材（先用 sc-content-mining）也不发布（公众号用 sc-publish-wechat，小红书用 sc-publish-xhs）；纯标题生成与短动态不在本 skill 范围。[Beta]
version: 0.4.0
---

# Writer: Outline + Draft

两阶段内容创作：把素材变成有主张、有口吻、可过质检的平台稿。

## 角色边界（必读）

本 skill 是**结构与口吻的生成器**，不是替代思考的工具。

- **交给 AI**：提炼主张、搭结构、按确定角度扩写、补背景、出口径质检建议。
- **必须由人提供**：第一手经历、核心判断与好恶、真实情绪节点；缺则写「未亲测」，禁止编造。

## Intents

- **内容大纲**：唯一核心主张、读者定位、结构与 Source map。
- **草稿生成**：按口吻规格扩成可发布 Markdown（及小红书图规格）。
- **平台适配**：公众号长文 / 小红书图文笔记。
- **写作质检**：四层自检出报告（发布合规另走 sc-content-review）。

## Progressive Disclosure

- [references/stages.md](references/stages.md) — **阶段 Schema 与验收**
- [references/voice.md](references/voice.md) — **口吻档案七维 + AI 味禁区**
- [references/writing-qc.md](references/writing-qc.md) — **四层写作质检**
- [references/craft.md](references/craft.md) — **可选写作技法库**
- [references/rewrite-examples.md](references/rewrite-examples.md) — **AI 稿 vs 人工改对照**
- [references/wechat-style.md](references/wechat-style.md) — **公众号平台规范**
- [references/xhs-style.md](references/xhs-style.md) — **小红书平台规范**
- [references/content-mining.md](references/content-mining.md) — **mining → writer 衔接**
- [references/xhs-to-images-handover.md](references/xhs-to-images-handover.md) — **writer → 图片 skill 衔接**
- [references/xhs-images-input-spec.md](references/xhs-images-input-spec.md) — **图片 skill 输入格式**
- [prompts/outline-wechat.md](prompts/outline-wechat.md) / [draft-wechat.md](prompts/draft-wechat.md) / [outline-xhs.md](prompts/outline-xhs.md) / [draft-xhs.md](prompts/draft-xhs.md) — **分平台执行步骤**

## Usage

> ⚠️ **Beta** — 以对话调用（prompt 驱动）为准；`./sc-run` CLI 尚未实现，请直接描述任务并引用 `prompts/` 流程。
