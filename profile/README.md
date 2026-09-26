English | [Tiếng Việt](https://github.com/HandLive/.github/blob/main/profile/README.vi.md)

# HandLive

HandLive is an open source project. It brings ecosystem-native features, such as Apple Handoff, to Android, so an Android device stays in sync with a Mac, iPhone and iPad, and those Apple devices sync back. End-to-end encryption stays on. The relay never reads content. Apache License 2.0. English is the default language, Vietnamese the second.

Design motto: *WebSocket for data, Bluetooth for voice.*

| Repository | Role | Language |
|------------|------|----------|
| [handlive](https://github.com/HandLive/handlive) | Documentation hub: specification, plan and design system. **Start here.** | Markdown, Python |
| [handlive-android](https://github.com/HandLive/handlive-android) | The Android phone app. Runs Handoff and the other continuity features | Kotlin |
| [handlive-apple](https://github.com/HandLive/handlive-apple) | Mac, iPhone and iPad apps. Receives data from Android and sends it back | Swift |
| [handlive-relay](https://github.com/HandLive/handlive-relay) | Relay for devices off the same network. Never reads content | Rust |
| [handlive-shared](https://github.com/HandLive/handlive-shared) | Shared test vectors, JSON Schemas, design tokens and UI strings | JSON, Python |

| Feature | macOS | iOS/iPadOS |
|---------|:-----:|:----------:|
| Two-way clipboard | ✅ | ✅ |
| Send and receive SMS | ✅ | ✅ |
| Call details and control | ✅ | ✅ (no audio) |
| Take calls on the computer (Bluetooth HFP, Opus/WebSocket fallback) | ✅ | ❌ |
| Virtual camera and microphone for meeting apps | ✅ | ❌ |

**Status:** Phase 1, clipboard sync between Android and Mac, is merged into `main`. The real-device checks of gate G1 are still open, so there is no release yet. Phase 2 is in progress: SMS, the iPhone and iPad app, the relay and push notifications. Roadmap: [docs/project-roadmap.md](https://github.com/HandLive/handlive/blob/main/docs/project-roadmap.md).

[Contributing](https://github.com/HandLive/.github/blob/main/CONTRIBUTING.md) · [Security](https://github.com/HandLive/.github/blob/main/SECURITY.md) · [Code of Conduct](https://github.com/HandLive/.github/blob/main/CODE_OF_CONDUCT.md)
