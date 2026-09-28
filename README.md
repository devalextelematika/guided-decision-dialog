# Guided Decision Dialog

A skills-only plugin for ChatGPT and Codex. Author: **Spidola**.

It helps clarify unresolved business or implementation choices through a short,
sequential dialogue: one consequential question at a time, concise mutually
exclusive options, and one evidence-based recommendation.

## Version

The initial release is `v1.0.0`.

## Contents

The distributable plugin is located at
`plugins/guided-decision-dialog/`.

Its `SKILL.md` is intentionally preserved without any text changes from the
source skill. The packaged skill therefore retains the name
`guided-decision-dialog`.

## Installation after publication

After the repository is public at
`devalextelematika/guided-decision-dialog`, add its marketplace:

```powershell
codex plugin marketplace add devalextelematika/guided-decision-dialog --sparse .agents/plugins
```

Restart the ChatGPT desktop app, open the Plugins directory, select the
**Guided Decision Dialog** marketplace, and install **Guided Decision Dialog**.

## License

This project is licensed under the [MIT License](LICENSE).
