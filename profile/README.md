English | [Tiếng Việt](https://github.com/HandLive/.github/blob/main/profile/README.vi.md)

# HandLive

**Your Android phone as the hub for your Mac, iPhone and iPad — clipboard, SMS, calls with live audio, and the phone's camera and microphone.** End-to-end encryption that cannot be turned off, a relay that never reads your content, and open source under the Apache License 2.0. Available in English and Vietnamese.

Design motto: *WebSocket for data, Bluetooth for voice.*

| Repository | Role | Language |
|------------|------|----------|
| [handlive](https://github.com/HandLive/handlive) | Hub: detailed design (the contract for all code), plan and design system. **Start here.** | Markdown, Python |
| [handlive-android](https://github.com/HandLive/handlive-android) | The phone app, hub of the system | Kotlin |
| [handlive-apple](https://github.com/HandLive/handlive-apple) | Mac, iPhone and iPad apps | Swift |
| [handlive-relay](https://github.com/HandLive/handlive-relay) | Cloud relay that never reads content | Rust |
| [handlive-shared](https://github.com/HandLive/handlive-shared) | Shared test vectors, JSON Schemas, design tokens and UI strings | JSON, Python |

| Feature | macOS | iOS/iPadOS |
|---------|:-----:|:----------:|
| Two-way clipboard | ✅ | ✅ |
| Send and receive SMS | ✅ | ✅ |
| Call details and control | ✅ | ✅ (no audio) |
| Take calls on the computer (Bluetooth HFP, Opus/WebSocket fallback) | ✅ | ❌ |
| Virtual camera and microphone for meeting apps | ✅ | ❌ |

**Status:** Phase 0 (scaffold, protocol, encryption, tokens, CI) is done; there is no user-facing feature yet. Next is Phase 1: clipboard sync between Android and Mac. Roadmap: [docs/project-roadmap.md](https://github.com/HandLive/handlive/blob/main/docs/project-roadmap.md).

[Contributing](https://github.com/HandLive/.github/blob/main/CONTRIBUTING.md) · [Security](https://github.com/HandLive/.github/blob/main/SECURITY.md) · [Code of Conduct](https://github.com/HandLive/.github/blob/main/CODE_OF_CONDUCT.md)
