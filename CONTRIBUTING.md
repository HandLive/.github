English | [Tiếng Việt](CONTRIBUTING.vi.md)

# Contributing to HandLive

HandLive is open source under the Apache License 2.0. It is made of five repositories that work together in **one workspace**:

| Repository | Contents |
|------------|----------|
| [handlive](https://github.com/HandLive/handlive) | Hub: detailed design (the contract for all code), implementation plan, design system, doc tools — **read first** |
| [handlive-android](https://github.com/HandLive/handlive-android) | Android app (Kotlin, Gradle) |
| [handlive-apple](https://github.com/HandLive/handlive-apple) | macOS and iOS/iPadOS apps (Swift) |
| [handlive-relay](https://github.com/HandLive/handlive-relay) | Zero-knowledge cloud relay (Rust) |
| [handlive-shared](https://github.com/HandLive/handlive-shared) | Shared contract: test vectors, JSON Schemas, design tokens, UI string catalog |

## Set up the workspace

```sh
git clone git@github.com:HandLive/handlive.git HandLive && cd HandLive
tools/workspace.sh clone git@github.com:HandLive   # clones the other repositories into android/, apple/, relay/, shared/
tools/workspace.sh hooks                            # enables the project's commit hooks
```

This layout is required: builds and tests read `../shared`, and the Apple tests and schema tools read `../docs`. Build and test commands: the hub's `docs/codebase-summary.md` and each repository's `README.md`.

## Workflow

1. Open an issue (templates provided) or pick a task card in the hub's `plans/20260925-implementation/`.
2. The docs are the contract between platforms. To change the protocol, error codes or UI text, change `docs/detailed-design/` first — both `X.md` and `X.vi.md`; `python3 tools/docs/validate_design_docs.py` must print `problems=0` and `python3 tools/docs/check_bilingual_docs.py` must pass — then `shared/` (vectors, schemas, string catalog), then platform code.
3. Work on a `feat/<slug>` or `fix/<slug>` branch in each repository concerned, using the same branch name across repositories; CI checks out the matching branch of handlive-shared and of the hub when it exists. Open pull requests against `main`; a change to `shared/` goes first, flagged so the other platforms re-run their tests.
4. Tests must pass before you open a pull request; CI rebuilds the workspace layout.

## Commits

- Conventional Commits in English, short: `feat(android): …`, `fix(relay): …`, `test(apple): …`, `docs: …`.
- Small and early: one commit per logical step (scaffold → module → tests → docs); a commit never spans two repositories.
- Under your real name, with a DCO sign-off: `git commit -s` adds `Signed-off-by: Name <email>`, certifying the [Developer Certificate of Origin](https://developercertificate.org). Never list an AI tool as author or co-author — the `.githooks/commit-msg` hook and the `commit-policy` CI job reject such commits.
- Never commit secrets, keys, certificates, dotenv files, or IDE and build output.

## Languages

- The product is multilingual: English (`en`) is the default language and Vietnamese (`vi`) the second. Every UI string has a stable key in `shared/strings/ui-strings.json` with both languages, and code never hard-codes user-facing text. English UI text follows Apple's English style (title-style capitalization for buttons, menus and window titles); Vietnamese UI text uses Apple-style tone marks (hóa, xóa, hủy, tùy).
- Documentation is bilingual: `X.md` in English (canonical) and `X.vi.md` in Vietnamese, with the same structure, updated in the same commit. Code, commit messages, error codes, logs and task reports are in English.

## New dependencies

Only Apache-2.0-compatible licenses: Apache, MIT, BSD, ISC, MPL-2.0, OFL (fonts). No GPL, LGPL or AGPL. Prefer libraries without proprietary components so the apps can also be distributed outside the app stores. Third-party assets bundled into an app are listed in that repository's `NOTICE`.

## Security

Never open a public issue for a vulnerability — see [SECURITY.md](SECURITY.md).
