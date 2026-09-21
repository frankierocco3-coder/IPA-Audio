# IPA-Audio

The recorded audio for [Speechcraft](https://frankierocco3-coder.github.io/IPA-App/),
published at `https://frankierocco3-coder.github.io/IPA-Audio/`.

**Do not edit this repository by hand.** Every file here is written by the
offline tools in the `IPA-App` repository (`tools/generate_voices.py`,
`tools/import_phonemes.py` and friends), which expect this repository to be
checked out beside it:

```
Agent-Workspace/
  ipa-trainer/   ← the app (IPA-App)
  IPA-Audio/     ← this repository
```

`index.json` and `phonemes-index.json` are the clip inventories the app
reads; `tools/audit_audio.py` in the app repository checks that they, the
files, and the quality flags all agree before the app deploys.

## Why it is a separate repository

Every GitHub Pages site under one account is the same web origin, so the app
can load audio from here with no exception to its strict same-origin rule —
while app deploys stop re-publishing ~300 MB of audio they did not change,
and each repository keeps its own size budget.

Only `.mp3` and `.json` files are ever published; see
`.github/workflows/deploy.yml`.
