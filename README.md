# Visual-First Editable PPT Skill

A reusable skill for the workflow:

**source material -> slide structure -> visual slide mockups -> approval -> editable PPT reconstruction -> render comparison**

The skill is intentionally designed for users who find that image-generated slide designs look better than PPT files generated directly.

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
