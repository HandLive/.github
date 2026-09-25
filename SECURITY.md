English | [Tiếng Việt](SECURITY.vi.md)

# Security Policy

HandLive handles people's clipboard, SMS, calls and camera with end-to-end encryption; security bugs have the highest priority.

## Reporting a vulnerability

- Do not open a public issue.
- Use **Report a vulnerability** (Security tab) on the affected repository, or email me@hxd.vn.
- Include the repository and commit, the platform, steps to reproduce, the impact, and a proof of concept if you have one.

## Our commitment

- We acknowledge reports within 7 days and send progress updates at least every 14 days.
- Coordinated disclosure: fix first, publish after — at most 90 days after the report, sooner once fixed.
- We credit reporters in the release notes if they wish. There is no bounty program yet.

## Scope

Every repository of the HandLive organization: encryption and pairing (XChaCha20-Poly1305, X25519, HKDF, QR/PIN), the WebSocket protocol, the zero-knowledge relay, on-device permissions and data, CI and the supply chain. Out of scope: vulnerabilities in operating systems or third-party libraries (report them upstream, and tell us if they affect HandLive), and attacks that need a rooted or jailbroken device.

## Supported versions

The project is in Phase 0 and has no release yet. Once released: the `main` branch and the latest release of each repository.
