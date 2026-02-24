<p align="center">
  <a href="https://github.com/usamadar/opencode-safe">
    <picture>
      <source srcset="packages/console/app/src/asset/logo-ornate-dark.svg" media="(prefers-color-scheme: dark)">
      <source srcset="packages/console/app/src/asset/logo-ornate-light.svg" media="(prefers-color-scheme: light)">
      <img src="packages/console/app/src/asset/logo-ornate-light.svg" alt="OpenCode Safe logo">
    </picture>
  </a>
</p>
<p align="center">Den open source AI-kodeagent.</p>
<p align="center">
  <a href="https://github.com/usamadar/opencode-safe/discussions"><img alt="Discussions" src="https://img.shields.io/github/discussions/usamadar/opencode-safe?style=flat-square" /></a>
  <a href="https://www.npmjs.com/package/opencode-safe"><img alt="npm" src="https://img.shields.io/npm/v/opencode-safe?style=flat-square" /></a>
  <a href="https://github.com/usamadar/opencode-safe/actions/workflows/publish.yml"><img alt="Build status" src="https://img.shields.io/github/actions/workflow/status/usamadar/opencode-safe/publish.yml?style=flat-square&branch=dev" /></a>
</p>

<p align="center">
  <a href="README.md">English</a> |
  <a href="README.zh.md">简体中文</a> |
  <a href="README.zht.md">繁體中文</a> |
  <a href="README.ko.md">한국어</a> |
  <a href="README.de.md">Deutsch</a> |
  <a href="README.es.md">Español</a> |
  <a href="README.fr.md">Français</a> |
  <a href="README.it.md">Italiano</a> |
  <a href="README.da.md">Dansk</a> |
  <a href="README.ja.md">日本語</a> |
  <a href="README.pl.md">Polski</a> |
  <a href="README.ru.md">Русский</a> |
  <a href="README.ar.md">العربية</a> |
  <a href="README.no.md">Norsk</a> |
  <a href="README.br.md">Português (Brasil)</a> |
  <a href="README.th.md">ไทย</a> |
  <a href="README.tr.md">Türkçe</a> |
  <a href="README.uk.md">Українська</a> |
  <a href="README.bn.md">বাংলা</a>
</p>

[![OpenCode Safe Terminal UI](packages/web/src/assets/lander/screenshot.png)](https://github.com/usamadar/opencode-safe)

---

> [!IMPORTANT]
> OpenCode Safe is an independent, privacy-first fork and is not affiliated with the upstream OpenCode project.

### Installation

```bash
# YOLO
curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash

# Pakkehåndteringer
npm i -g opencode-safe@latest        # eller bun/pnpm/yarn
scoop install opencode-safe             # Windows
choco install opencode-safe             # Windows
brew install usamadar/tap/opencode-safe # macOS og Linux (anbefalet, altid up to date)
brew install opencode-safe              # macOS og Linux (officiel brew formula, opdateres sjældnere)
sudo pacman -S opencode-safe            # Arch Linux (Stable)
paru -S opencode-safe-bin               # Arch Linux (Latest from AUR)
mise use -g opencode-safe               # alle OS
nix run nixpkgs#opencode-safe           # eller github:usamadar/opencode-safe for nyeste dev-branch
```

> [!TIP]
> Fjern versioner ældre end 0.1.x før installation.

### Desktop-app (BETA)

OpenCode Safe findes også som desktop-app. Download direkte fra [releases-siden](https://github.com/usamadar/opencode-safe/releases) eller [GitHub Releases](https://github.com/usamadar/opencode-safe/releases).

| Platform              | Download                              |
| --------------------- | ------------------------------------- |
| macOS (Apple Silicon) | `opencode-safe-desktop-darwin-aarch64.dmg` |
| macOS (Intel)         | `opencode-safe-desktop-darwin-x64.dmg`     |
| Windows               | `opencode-safe-desktop-windows-x64.exe`    |
| Linux                 | `.deb`, `.rpm`, eller AppImage        |

```bash
# macOS (Homebrew)
brew install --cask opencode-safe-desktop
# Windows (Scoop)
scoop bucket add extras; scoop install extras/opencode-safe-desktop
```

#### Installationsmappe

Installationsscriptet bruger følgende prioriteringsrækkefølge for installationsstien:

1. `$OPENCODE_SAFE_INSTALL_DIR` - Tilpasset installationsmappe
2. `$XDG_BIN_DIR` - Sti der følger XDG Base Directory Specification
3. `$HOME/bin` - Standard bruger-bin-mappe (hvis den findes eller kan oprettes)
4. `$HOME/.opencode-safe/bin` - Standard fallback

```bash
# Eksempler
OPENCODE_SAFE_INSTALL_DIR=/usr/local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
XDG_BIN_DIR=$HOME/.local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
```

### Agents

OpenCode Safe har to indbyggede agents, som du kan skifte mellem med `Tab`-tasten.

- **build** - Standard, agent med fuld adgang til udviklingsarbejde
- **plan** - Skrivebeskyttet agent til analyse og kodeudforskning
  - Afviser filredigering som standard
  - Spørger om tilladelse før bash-kommandoer
  - Ideel til at udforske ukendte kodebaser eller planlægge ændringer

Derudover findes der en **general**-subagent til komplekse søgninger og flertrinsopgaver.
Den bruges internt og kan kaldes via `@general` i beskeder.

Læs mere om [agents](https://github.com/usamadar/opencode-safe#agents).

### Dokumentation

For mere info om konfiguration af OpenCode Safe, [**se vores docs**](https://github.com/usamadar/opencode-safe#readme).

### Bidrag

Hvis du vil bidrage til OpenCode Safe, så læs vores [contributing docs](./CONTRIBUTING.md) før du sender en pull request.

### Bygget på OpenCode Safe

Hvis du arbejder på et projekt der er relateret til OpenCode Safe og bruger "opencode-safe" som en del af navnet; f.eks. "opencode-safe-dashboard" eller "opencode-safe-mobile", så tilføj en note i din README, der tydeliggør at projektet ikke er bygget af OpenCode Safe-teamet og ikke er tilknyttet os på nogen måde.

### FAQ

#### Hvordan adskiller dette sig fra Claude Code?

Det minder meget om Claude Code i forhold til funktionalitet. Her er de vigtigste forskelle:

- 100% open source
- Ikke låst til en udbyder. Selvom vi anbefaler modellerne via [OpenCode Safe](https://github.com/usamadar/opencode-safe#readme); kan OpenCode Safe bruges med Claude, OpenAI, Google eller endda lokale modeller. Efterhånden som modeller udvikler sig vil forskellene mindskes og priserne falde, så det er vigtigt at være provider-agnostic.
- LSP-support out of the box
- Fokus på TUI. OpenCode Safe er bygget af neovim-brugere og skaberne af [terminal.shop](https://terminal.shop); vi vil skubbe grænserne for hvad der er muligt i terminalen.
- Klient/server-arkitektur. Det kan f.eks. lade OpenCode Safe køre på din computer, mens du styrer den eksternt fra en mobilapp. Det betyder at TUI-frontend'en kun er en af de mulige clients.

---

**Bliv en del af vores community** [Discord](https://github.com/usamadar/opencode-safe/discussions) | [X.com](https://github.com/usamadar/opencode-safe)
