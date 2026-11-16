# Studio 87 standards

One page of rules so every repo, every chat and the website stay consistent. Read it before you change a repo. If a rule is wrong or missing, say so in your reply instead of working around it.

## 1. Every public repo has

| File | What |
|---|---|
| `README.md` | Follows section 5. |
| `LICENSE` | AGPL-3.0-or-later (unless the repo already says otherwise). |
| `.github/FUNDING.yml` | `ko_fi: studio87` |
| `docs/screenshot.png` | The plugin window only (no page, no browser). At least 1600 px wide. Replace it whenever the interface changes. |
| `docs/cover.png` | Only for repos with no interface (units, libraries): an illustration in the brand style. |
| `docs/mockup/index.html` | The interactive mockup, one standalone file (section 2). |
| `docs/mockup/fonts/` | The fonts the mockup uses, with their license text. |
| `docs/audio/` | Optional sound clips with `clips.json` (section 4). |

## 2. The interactive mockup

- **One file** that works by double-clicking it. No Claude Design runtime, no `support.js`, no build step.
- **No outside requests.** No Google Fonts, no CDN, no analytics. Fonts are bundled in `docs/mockup/fonts/` and loaded with a relative `@font-face` (`src: url(fonts/name.woff2)`).
- It must look right when shown inside a frame about 1100 px wide, and the plugin window must scale to the page width on load. Dragging the edges must not be able to push the plugin out of view.
- Put no data-handling claims in the page text ("collects nothing", "no telemetry"). See section 8.
- Page title is the plugin name. No leftover version notes, no "design mockup" paragraphs on the page itself.

## 3. Screenshots

- Plugin window only, 100% scale, default preset, nothing selected or hovered.
- Same dark colors as the real plugin. No device frames, no watermarks.

## 4. Sound clips

- Rendered with the real engine of the plugin, never recorded from the mockup.
- 8 to 12 seconds, `.mp3`, under 200 KB each, level-matched, no clipping.
- Musically sensible: notes in a range that is clearly audible on laptop speakers (no sub-only bass), real melodies and rhythm, a sound that matches its preset name.
- `docs/audio/clips.json` is a list of `{ "file", "preset", "description" }` (optional `"category"`). One plain sentence per description, no hype.

## 5. README order

1. Title (plugin name)
2. Ko-fi banner (`https://raw.githubusercontent.com/SpeakingColors/.github/main/assets/kofi-banner.svg`)
3. Screenshot or cover
4. One or two plain sentences: what it is, formats, platforms
5. **Status** (honest: design mockup, test build, released)
6. **Download** (link to Releases)
7. Controls or features, only what exists
8. **Support** (Ko-fi badge and one friendly line)
9. **License**, and the "not affiliated with ..." line whenever a company or product is named

Plain words. Say what it is, not how great it is. No data or privacy promises in READMEs.

## 6. GitHub description, topics and settings

- Description: one sentence, "Free open source <what> (<format>) for <platform>." Say if it is a test build or a design mockup.
- Topics always include `open-source` and, for plugins, `audio-plugin`, `vst3`, `juce`, `linux-audio`, `music-production`, `free-vst`, plus what it is (`compressor`, `synthesizer`, ...).
- Issues, Wikis, Discussions, Projects and Pull requests are **off**. Commit comments are **off**. The repo is not in the Archive Program. Forks are welcome: that is how anyone builds on a project.

## 7. Names, one project one repo

- One project lives in exactly one repo. No copies of the same book, plugin or tool in two repos.
- If you rename or delete a repo, update `gearupdater` (its product list and mockup) and tell the website session.
- Display names are written the same everywhere (README title, description, website, Gear Updater).

## 8. Honesty

- Never claim something you did not check in the code or on the machine.
- Statements about data handling live in one place only: the website's Privacy page. Everywhere else, leave them out.
- Say "test build" for pre-releases. Say "design mockup" when there is no plugin yet.

## 9. Brand

- Pink `#ff6aa5`, teal `#2dd4bf`, yellow `#ffd23f`, dark `#141618`, cream `#f6efe3`.
- Website type: Bricolage Grotesque (headings) and DM Sans (text). Plugin interfaces: Barlow Condensed and JetBrains Mono.
- The cat is the mascot. Wood side panels belong to plugin windows, not the website.

## 10. The website

- `SpeakingColors.github.io` is rebuilt from the repos automatically, about every 30 minutes. **Do not edit it from a plugin chat.** Fix the repo and the website follows.
- Anything that must show up on the website goes in the files listed in section 1.

## 11. When you finish a job

Reply with a short list: repo, what changed, check passed or not, and anything you could not do and why. Do not ask which job to do first: do them in the order given.
