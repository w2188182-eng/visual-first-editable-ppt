# Visual-First Editable PPT Skill

A reusable skill for the workflow:

**source material -> slide structure -> visual slide mockups -> approval -> editable PPT reconstruction -> render comparison**

The skill is intentionally designed for users who find that image-generated slide designs look better than PPT files generated directly.

## 默认字体与文本框规则

- 字体可以由用户指定，也可以随时修改。优先采用用户最新指定的字体；只有未指定的部分才默认使用微软雅黑（Microsoft YaHei），包括英文、数字和标点。若要求保留模板字体，则未另行指定的部分沿用模板。
- 支持按范围指定，例如“全文宋体”“标题黑体”或“中文微软雅黑、英文 Arial”。默认值不能覆盖用户选择；后续改字体也不受默认值限制。
- 同一段落或同一内容块使用一个文本框，通过框内换行、段落和列表格式排版，不按每一行或每个列表项单独建框。
- 不同内容可以分别建框，例如小标题和正文、不同卡片或独立图示标签。
- 同一段中的红字、加粗、英文缩写使用框内局部格式，不拆框。修改文字或调整框宽时，整个内容块应能一起重排。

## Files

- `SKILL.md` — main reusable workflow.
- `agents/openai.yaml` — OpenAI UI metadata.
- `references/qa-checklist.md` — reconstruction QA checklist.
- `templates/request-template.md` — copy-paste invocation template.

## ChatGPT

ChatGPT Skills use a `SKILL.md`-based reusable workflow format. Upload/import this skill package in a Skills-enabled ChatGPT workspace, then invoke it by name or let ChatGPT select it when the request matches.

## Codex

The folder can be used as a personal Codex skill. Install/copy the complete `visual-first-editable-ppt` directory into your Codex skills location, or publish the folder to a Git repository and install it with Codex's skill installer. Restart Codex after installation if the newly installed skill is not discovered immediately.

A simple invocation is:

`Use $visual-first-editable-ppt for these source files.`

Then attach the source material and describe the target audience/style if needed.

## Notes

This skill does not force every decorative element to be editable. It uses a hybrid model: likely-to-change content remains native PowerPoint objects, while complex decorative/illustrative elements may remain images.
