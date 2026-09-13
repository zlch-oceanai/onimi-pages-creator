# Onimi Pages Creator

**English** | [简体中文](docs/zh-CN/README.md)

Create, refine, validate, and preview polished standalone HTML in your own agent workspace.

## Install

Check the [verified channel states](https://downloads.onimi.ai/skills/manifest.json) before choosing a
source. npm's `latest` release and the ClawHub listing should be used only when their channels are
marked available.

```sh
npx --registry=https://registry.npmjs.org onimi-pages-creator@latest install --agent codex
```

Other sources:

- Direct download: read `skills.creator.archive.url`, `sha256`, and `size` from the
  [stable manifest](https://downloads.onimi.ai/skills/manifest.json), then verify the immutable archive
- GitHub: `npx --registry=https://registry.npmjs.org skills@1.5.26 add zlch-oceanai/onimi-pages-creator --skill onimi-pages-creator --global`
- ClawHub (CLI requires Node.js 22+): `npx --registry=https://registry.npmjs.org clawhub@0.23.3 install @mariohazy/onimi-pages-creator`

Every source contains the complete Skill and local validator. Existing installations are preserved.
See [INSTALL.md](INSTALL.md) for client directories, integrity checks, and update behavior.

## Use

Ask the agent for the artifact you need, for example:

> Create a responsive bilingual product launch page as one self-contained HTML file. Validate it and
> preview both languages on desktop and mobile.

Creator works locally and does not send the prompt or artifact to Onimi Pages. It guides the agent to
choose an intentional visual direction, implement working keyboard-accessible interactions, label
fictional data, and inspect the result in a browser. Run the bundled validator directly when needed:

```sh
node skills/onimi-pages-creator/scripts/validate-html.mjs /absolute/path/to/page.html
```

Creation does not authorize publication. Install the separate `onimi-pages-publish` Skill and complete
its browser OAuth flow only when you decide to publish.

## Repository layout

- `skills/onimi-pages-creator/`: complete Skill, references, validator, update manager, and hash receipt.
- `bin/`: dependency-free npm installer with no lifecycle scripts.
- `docs/zh-CN/`: Chinese README and installation guide.

The repository contains public distribution files only and uses the MIT-0 license. It contains no
application source, credentials, hosted user content, or test-service configuration.

## 0.1.0

- Standalone Creator repository and npm package.
- Bilingual installation guides and local-change-safe direct-download updates.
- Explicit separation between local creation and optional authenticated publishing.
