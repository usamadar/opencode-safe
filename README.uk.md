<p align="center">
  <a href="https://github.com/usamadar/opencode-safe">
    <picture>
      <source srcset="packages/console/app/src/asset/logo-ornate-dark.svg" media="(prefers-color-scheme: dark)">
      <source srcset="packages/console/app/src/asset/logo-ornate-light.svg" media="(prefers-color-scheme: light)">
      <img src="packages/console/app/src/asset/logo-ornate-light.svg" alt="OpenCode Safe logo">
    </picture>
  </a>
</p>
<p align="center">AI-агент для програмування з відкритим кодом.</p>
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
  <a href="README.bs.md">Bosanski</a> |
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

### Встановлення

```bash
# YOLO
curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash

# Менеджери пакетів
npm i -g opencode-safe@latest        # або bun/pnpm/yarn
scoop install opencode-safe             # Windows
choco install opencode-safe             # Windows
brew install usamadar/tap/opencode-safe # macOS і Linux (рекомендовано, завжди актуально)
brew install opencode-safe              # macOS і Linux (офіційна формула Homebrew, оновлюється рідше)
sudo pacman -S opencode-safe            # Arch Linux (Stable)
paru -S opencode-safe-bin               # Arch Linux (Latest from AUR)
mise use -g opencode-safe               # Будь-яка ОС
nix run nixpkgs#opencode-safe           # або github:usamadar/opencode-safe для найновішої dev-гілки
```

> [!TIP]
> Перед встановленням видаліть версії старші за 0.1.x.

### Десктопний застосунок (BETA)

OpenCode Safe також доступний як десктопний застосунок. Завантажуйте напряму зі [сторінки релізів](https://github.com/usamadar/opencode-safe/releases) або [GitHub Releases](https://github.com/usamadar/opencode-safe/releases).

| Платформа             | Завантаження                          |
| --------------------- | ------------------------------------- |
| macOS (Apple Silicon) | `opencode-safe-desktop-darwin-aarch64.dmg` |
| macOS (Intel)         | `opencode-safe-desktop-darwin-x64.dmg`     |
| Windows               | `opencode-safe-desktop-windows-x64.exe`    |
| Linux                 | `.deb`, `.rpm` або AppImage           |

```bash
# macOS (Homebrew)
brew install --cask opencode-safe-desktop
# Windows (Scoop)
scoop bucket add extras; scoop install extras/opencode-safe-desktop
```

#### Каталог встановлення

Скрипт встановлення дотримується такого порядку пріоритету для шляху встановлення:

1. `$OPENCODE_SAFE_INSTALL_DIR` - Користувацький каталог встановлення
2. `$XDG_BIN_DIR` - Шлях, сумісний зі специфікацією XDG Base Directory
3. `$HOME/bin` - Стандартний каталог користувацьких бінарників (якщо існує або його можна створити)
4. `$HOME/.opencode-safe/bin` - Резервний варіант за замовчуванням

```bash
# Приклади
OPENCODE_SAFE_INSTALL_DIR=/usr/local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
XDG_BIN_DIR=$HOME/.local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
```

### Агенти

OpenCode Safe містить два вбудовані агенти, між якими можна перемикатися клавішею `Tab`.

- **build** - Агент за замовчуванням із повним доступом для завдань розробки
- **plan** - Агент лише для читання для аналізу та дослідження коду
  - За замовчуванням забороняє редагування файлів
  - Запитує дозвіл перед запуском bash-команд
  - Ідеально підходить для дослідження незнайомих кодових баз або планування змін

Також доступний допоміжний агент **general** для складного пошуку та багатокрокових завдань.
Він використовується всередині системи й може бути викликаний у повідомленнях через `@general`.

Дізнайтеся більше про [agents](https://github.com/usamadar/opencode-safe#agents).

### Документація

Щоб дізнатися більше про налаштування OpenCode Safe, [**перейдіть до нашої документації**](https://github.com/usamadar/opencode-safe#readme).

### Внесок

Якщо ви хочете зробити внесок в OpenCode Safe, будь ласка, прочитайте нашу [документацію для контриб'юторів](./CONTRIBUTING.md) перед надсиланням pull request.

### Проєкти на базі OpenCode Safe

Якщо ви працюєте над проєктом, пов'язаним з OpenCode Safe, і використовуєте "opencode-safe" у назві, наприклад "opencode-safe-dashboard" або "opencode-safe-mobile", додайте примітку до свого README.
Уточніть, що цей проєкт не створений командою OpenCode Safe і жодним чином не афілійований із нами.

### FAQ

#### Чим це відрізняється від Claude Code?

За можливостями це дуже схоже на Claude Code. Ось ключові відмінності:

- 100% open source
- Немає прив'язки до конкретного провайдера. Ми рекомендуємо моделі, які надаємо через [OpenCode Safe](https://github.com/usamadar/opencode-safe#readme), але OpenCode Safe також працює з Claude, OpenAI, Google і навіть локальними моделями. З розвитком моделей різниця між ними зменшуватиметься, а ціни падатимуть, тому незалежність від провайдера має значення.
- Підтримка LSP з коробки
- Фокус на TUI. OpenCode Safe створено користувачами neovim та авторами [terminal.shop](https://terminal.shop); ми й надалі розширюватимемо межі можливого в терміналі.
- Клієнт-серверна архітектура. Наприклад, це дає змогу запускати OpenCode Safe на вашому комп'ютері й керувати ним віддалено з мобільного застосунку, тобто TUI-фронтенд - лише один із можливих клієнтів.

---

**Приєднуйтеся до нашої спільноти** [Discord](https://github.com/usamadar/opencode-safe/discussions) | [X.com](https://github.com/usamadar/opencode-safe)
