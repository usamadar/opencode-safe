<p align="center">
  <a href="https://github.com/usamadar/opencode-safe">
    <picture>
      <source srcset="packages/console/app/src/asset/logo-ornate-dark.svg" media="(prefers-color-scheme: dark)">
      <source srcset="packages/console/app/src/asset/logo-ornate-light.svg" media="(prefers-color-scheme: light)">
      <img src="packages/console/app/src/asset/logo-ornate-light.svg" alt="OpenCode Safe logo">
    </picture>
  </a>
</p>
<p align="center">Открытый AI-агент для программирования.</p>
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
  <a href="README.bn.md">বাংলা</a> |
  <a href="README.gr.md">Ελληνικά</a> |
  <a href="README.vi.md">Tiếng Việt</a>
</p>

[![OpenCode Safe Terminal UI](packages/web/src/assets/lander/screenshot.png)](https://github.com/usamadar/opencode-safe)

---

> [!IMPORTANT]
> OpenCode Safe is an independent, privacy-first fork and is not affiliated with the upstream OpenCode project.

### Установка

```bash
# YOLO
curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash

# Менеджеры пакетов
npm i -g opencode-safe@latest        # или bun/pnpm/yarn
scoop install opencode-safe             # Windows
choco install opencode-safe             # Windows
brew install usamadar/tap/opencode-safe # macOS и Linux (рекомендуем, всегда актуально)
brew install opencode-safe              # macOS и Linux (официальная формула brew, обновляется реже)
sudo pacman -S opencode-safe            # Arch Linux (Stable)
paru -S opencode-safe-bin               # Arch Linux (Latest from AUR)
mise use -g opencode-safe               # любая ОС
nix run nixpkgs#opencode-safe           # или github:usamadar/opencode-safe для самой свежей ветки dev
```

> [!TIP]
> Перед установкой удалите версии старше 0.1.x.

### Десктопное приложение (BETA)

OpenCode Safe также доступен как десктопное приложение. Скачайте его со [страницы релизов](https://github.com/usamadar/opencode-safe/releases) или с [GitHub Releases](https://github.com/usamadar/opencode-safe/releases).

| Платформа             | Загрузка                              |
| --------------------- | ------------------------------------- |
| macOS (Apple Silicon) | `opencode-safe-desktop-darwin-aarch64.dmg` |
| macOS (Intel)         | `opencode-safe-desktop-darwin-x64.dmg`     |
| Windows               | `opencode-safe-desktop-windows-x64.exe`    |
| Linux                 | `.deb`, `.rpm` или AppImage           |

```bash
# macOS (Homebrew)
brew install --cask opencode-safe-desktop
# Windows (Scoop)
scoop bucket add extras; scoop install extras/opencode-safe-desktop
```

#### Каталог установки

Скрипт установки выбирает путь установки в следующем порядке приоритета:

1. `$OPENCODE_SAFE_INSTALL_DIR` - Пользовательский каталог установки
2. `$XDG_BIN_DIR` - Путь, совместимый со спецификацией XDG Base Directory
3. `$HOME/bin` - Стандартный каталог пользовательских бинарников (если существует или можно создать)
4. `$HOME/.opencode-safe/bin` - Fallback по умолчанию

```bash
# Примеры
OPENCODE_SAFE_INSTALL_DIR=/usr/local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
XDG_BIN_DIR=$HOME/.local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
```

### Agents

В OpenCode Safe есть два встроенных агента, между которыми можно переключаться клавишей `Tab`.

- **build** - По умолчанию, агент с полным доступом для разработки
- **plan** - Агент только для чтения для анализа и изучения кода
  - По умолчанию запрещает редактирование файлов
  - Запрашивает разрешение перед выполнением bash-команд
  - Идеален для изучения незнакомых кодовых баз или планирования изменений

Также включен сабагент **general** для сложных поисков и многошаговых задач.
Он используется внутренне и может быть вызван в сообщениях через `@general`.

Подробнее об [agents](https://github.com/usamadar/opencode-safe#agents).

### Документация

Больше информации о том, как настроить OpenCode Safe: [**наши docs**](https://github.com/usamadar/opencode-safe#readme).

### Вклад

Если вы хотите внести вклад в OpenCode Safe, прочитайте [contributing docs](./CONTRIBUTING.md) перед тем, как отправлять pull request.

### Разработка на базе OpenCode Safe

Если вы делаете проект, связанный с OpenCode Safe, и используете "opencode-safe" как часть имени (например, "opencode-safe-dashboard" или "opencode-safe-mobile"), добавьте примечание в README, чтобы уточнить, что проект не создан командой OpenCode Safe и не аффилирован с нами.

### FAQ

#### Чем это отличается от Claude Code?

По возможностям это очень похоже на Claude Code. Вот ключевые отличия:

- 100% open source
- Не привязано к одному провайдеру. Мы рекомендуем модели из [OpenCode Safe](https://github.com/usamadar/opencode-safe#readme); но OpenCode Safe можно использовать с Claude, OpenAI, Google или даже локальными моделями. По мере развития моделей разрыв будет сокращаться, а цены падать, поэтому важна независимость от провайдера.
- Поддержка LSP из коробки
- Фокус на TUI. OpenCode Safe построен пользователями neovim и создателями [terminal.shop](https://terminal.shop); мы будем раздвигать границы того, что возможно в терминале.
- Архитектура клиент/сервер. Например, это позволяет запускать OpenCode Safe на вашем компьютере, а управлять им удаленно из мобильного приложения. Это значит, что TUI-фронтенд - лишь один из возможных клиентов.

---

**Присоединяйтесь к нашему сообществу** [Discord](https://github.com/usamadar/opencode-safe/discussions) | [X.com](https://github.com/usamadar/opencode-safe)
