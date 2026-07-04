<div align="center">
  <img src="./assets/text.png" alt="CamouChat" />
</div>

<div align="center">
  <h1>🦊 CamouChat Ecosystem</h1>
  <p><b>The High-Performance, Stealth-Aware Automation Framework</b></p>
</div>

<p align= "center">
  <a href="https://github.com/CamouChat-Team/camouchat-core">
      <img src="https://img.shields.io/badge/Status-Active-brightgreen.svg" alt="Status" />
  </a>
  <a href="https://pypi.org/project/camouchat/">
      <img src="https://img.shields.io/pypi/v/camouchat?label=camouchat-core&color=blue" />
  </a>
  <a href="https://opensource.org/licenses/MIT">
      <img src="https://img.shields.io/badge/License-MIT-yellow.svg" />
  </a>
</p>

---

## Introduction to CamouChat

CamouChat is an advanced, strictly decoupled ecosystem designed for researchers and developers to build high-performance Web Automation agents safely. Initially built for highly secured chat applications like WhatsApp, it utilizes **Camoufox** to achieve industry-leading anti-detection capabilities.

It provides a standardized framework incorporating **end-to-end encrypted local storage**, **isolated sandbox profiling**, and **humanized interaction schemas** — completely removing the fragility associated with raw DOM scraping or unsecured automation libraries.

This repository serves as the central hub and entry point for the entire CamouChat plugin ecosystem.

> [!IMPORTANT]
> **v0.7.0 Update** — CamouChat is now a decoupled plugin ecosystem. The `camouchat` package on PyPI is the umbrella entry point. WhatsApp automation lives in **[`camouchat-whatsapp`](https://pypi.org/project/camouchat-whatsapp/)** — install that for full functionality. Existing users of the old monolithic `camouchat` package: no API changes, just point your install to `camouchat-whatsapp` going forward.

---

## Why CamouChat?

Before building CamouChat, maintaining reliable web automation pipelines across restricted platforms presented major challenges:

* **Fragile Automation**: Hardcoded CSS selectors break constantly on platform UI updates. 
* **Bot Identification**: Basic Puppeteer/Playwright instances trigger modern captchas and integrity scanners immediately.
* **Account Risk**: Lack of isolated cookie/cache containment leads to swift cross-account detection and IP shadowbans.
* **Architecture Bloat**: Existing libraries are typically monolithic, tightly coupled wrappers that force you into a single way of handling tasks.

**CamouChat solves this by establishing a protocol-driven SDK, routing actions through secure internal APIs (injecting JS bridges without triggering scanners) and standardizing storage schemas globally.**

---

## 🧩 The Plugin Ecosystem

Starting from `v0.7.0`, CamouChat has been strictly decoupled into specialized plugins. You install exactly what you need.

### 1. [camouchat-core](https://github.com/CamouChat-Team/camouchat-core) — The Foundation &nbsp; [![PyPI](https://img.shields.io/pypi/v/camouchat-core?color=blue)](https://pypi.org/project/camouchat-core/)
The required central SDK interface. Provides the foundational structures:
- Standardized `typing.Protocol` contracts for interoperability.
- Asynchronous Logging Engine (`concurrent-log-handler`).
- Strict AES-GCM-256 Storage & Metadata interfaces.

### 2. [camouchat-browser](https://github.com/CamouChat-Team/camouchat-browser) — The Engine &nbsp; [![PyPI](https://img.shields.io/pypi/v/camouchat-browser?color=blue)](https://pypi.org/project/camouchat-browser/)
The stealth browser layer built for Web interactions.
- Embeds [Camoufox](https://camoufox.com/) for deep connection and JS fingerprint spoofing.
- Generates dynamic hardware profiles via `browserforge`.
- Automated OS-aware profile sandboxing and encryption.

### 3. [camouchat-whatsapp](https://github.com/CamouChat-Team/camouchat-whatsapp) — The Implementation &nbsp; [![PyPI](https://img.shields.io/pypi/v/camouchat-whatsapp?color=blue)](https://pypi.org/project/camouchat-whatsapp/)
A platform-specific plugin leveraging the Core and Browser ecosystems to automate WhatsApp Web perfectly.
- Complete internal API bridge using [wa-js](https://github.com/wppconnect-team/wa-js) natively.
- Zero DOM Scraping — Event-driven interaction.
- Support for complex media fetching, stealth timing, and fully-typed async architectures.

---

## 🚀 Quick Install

> 📦 **Full WhatsApp plugin → [`camouchat-whatsapp` on PyPI](https://pypi.org/project/camouchat-whatsapp/)** — detailed docs, changelog, and API reference live there.

To build a full, automated WhatsApp agent utilizing the Camoufox engine, install the ecosystem via `uv` or `pip`:

### Using `uv` (Recommended)
```bash
uv add camouchat-whatsapp "camoufox[geoip]"
uv run python -m camoufox fetch
```

### Using `pip`
```bash
pip install camouchat-whatsapp "camoufox[geoip]"
python -m camoufox fetch
```

> [!WARNING]
> Running `camoufox fetch` is a **mandatory** one-time step that downloads the compiled Firefox binaries. Normal package managers cannot perform this hook automatically.

---

## 📚 Global Documentation

* 📖 **Core Architecture**: [Link](https://github.com/CamouChat-Team/camouchat-core/tree/main/docs)
* 📖 **Browser Configurations**: [Link](https://github.com/CamouChat-Team/camouchat-browser/tree/main/docs)
* 📖 **WhatsApp API & Models**: [Link](https://github.com/CamouChat-Team/camouchat-whatsapp/tree/main/docs)

---

## ⚖️ Security & Ethics

CamouChat provides powerful browser automation and stealth infrastructure. With this power comes the responsibility to use it ethically and in compliance with the rules of the platforms you interact with. 

Please read our mandatory **[Security & Ethics Guidelines](https://github.com/CamouChat-Team/CamouChat/blob/main/SECURITY.md)** regarding acceptable use, anti-spam policies, and anti-detection disclaimers before utilizing the ecosystem.

---

## 👩‍💻 Contributor Navigation & Verification Workflow

CamouChat follows a plugin-based and modular architecture.
This repository acts as the umbrella repository for the complete CamouChat ecosystem.

Many components, integrations, automation modules, and internal systems are maintained across multiple repositories under the `CamouChat-Team` organization. These repositories are not isolated projects — together they form the complete CamouChat platform.

To avoid contributor confusion:

* Contributors should explore all repositories under the organization before starting development.
* Issues, plugins, integrations, and platform-specific implementations may exist in separate repositories.
* Some repositories may depend on or extend functionality from others.
* Contributors must always read the `CODE_OF_CONDUCT.md` and contribution guidelines of the target repository before contributing.

### Contribution Workflow

Contributors are expected to work in the actual implementation/plugin repositories where the real codebase exists.

**Contribution Steps:**

1. **Select and work on issues** in the appropriate plugin/code repository.
2. **After the PR is successfully merged** in the target repository, open a verification issue in the umbrella `CamouChat` repository.
3. **Raise an Issue**, the verification issue must contain:
   * Contributor name
   * Open source program/organization name (if applicable)
   * Actual merged PR link
   * Repository name
   * Short summary of the contribution
4. **After admin verification:** Contributor may create a PR in the umbrella repository updating the contribution tracking file (`PR_validation.md`).

This workflow exists to maintain centralized contribution tracking, contributor visibility, and ecosystem-level coordination across the modular CamouChat architecture.

---

## 🤝 Community & Support

* [Code of Conduct](https://github.com/CamouChat-Team/camouchat-core/blob/main/CODE_OF_CONDUCT.md)
* [Contribution Guidelines](https://github.com/CamouChat-Team/CamouChat/blob/main/CONTRIBUTING.md)
* [Changelog / Release Notes](https://github.com/CamouChat-Team/camouchat-core/releases)
* Submitting issues: Please file platform-specific issues directly in the corresponding plugin repository (`camouchat-whatsapp`, etc.).

---

<p align="center">
  Built with ❤️ by BITS-Rohit and the CamouChat community
</p>

## ✨ README Improvement Notes

### 📌 Formatting Enhancements Needed
- Improve heading hierarchy for better readability
- Ensure consistent spacing between sections
- Use proper Markdown formatting for code blocks and lists
- Align all installation and usage steps properly

### 🚀 Suggested Structure Upgrade
- Introduction
- Features
- Tech Stack
- Installation
- Usage
- Project Structure
- Contribution Guidelines
- License

### 🛠️ Documentation Improvements
- Add badges (optional): build, license, contributors
- Add screenshots for better UI understanding
- Standardize code blocks for commands

### 🎯 Goal
Improve onboarding experience for new contributors and users by making README more structured, readable, and professional.

