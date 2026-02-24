<p align="center">
  <a href="https://github.com/usamadar/opencode-safe">
    <picture>
      <source srcset="packages/console/app/src/asset/logo-ornate-dark.svg" media="(prefers-color-scheme: dark)">
      <source srcset="packages/console/app/src/asset/logo-ornate-light.svg" media="(prefers-color-scheme: light)">
      <img src="packages/console/app/src/asset/logo-ornate-light.svg" alt="Logo do OpenCode Safe">
    </picture>
  </a>
</p>
<p align="center">O agente de programação com IA de código aberto.</p>
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

### Instalação

```bash
# YOLO
curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash

# Gerenciadores de pacotes
npm i -g opencode-safe@latest        # ou bun/pnpm/yarn
scoop install opencode-safe             # Windows
choco install opencode-safe             # Windows
brew install usamadar/tap/opencode-safe # macOS e Linux (recomendado, sempre atualizado)
brew install opencode-safe              # macOS e Linux (fórmula oficial do brew, atualiza menos)
sudo pacman -S opencode-safe            # Arch Linux (Stable)
paru -S opencode-safe-bin               # Arch Linux (Latest from AUR)
mise use -g opencode-safe               # qualquer sistema
nix run nixpkgs#opencode-safe           # ou github:usamadar/opencode-safe para a branch dev mais recente
```

> [!TIP]
> Remova versões anteriores a 0.1.x antes de instalar.

### App desktop (BETA)

O OpenCode Safe também está disponível como aplicativo desktop. Baixe diretamente pela [página de releases](https://github.com/usamadar/opencode-safe/releases) ou em [GitHub Releases](https://github.com/usamadar/opencode-safe/releases).

| Plataforma            | Download                              |
| --------------------- | ------------------------------------- |
| macOS (Apple Silicon) | `opencode-safe-desktop-darwin-aarch64.dmg` |
| macOS (Intel)         | `opencode-safe-desktop-darwin-x64.dmg`     |
| Windows               | `opencode-safe-desktop-windows-x64.exe`    |
| Linux                 | `.deb`, `.rpm` ou AppImage            |

```bash
# macOS (Homebrew)
brew install --cask opencode-safe-desktop
# Windows (Scoop)
scoop bucket add extras; scoop install extras/opencode-safe-desktop
```

#### Diretório de instalação

O script de instalação respeita a seguinte ordem de prioridade para o caminho de instalação:

1. `$OPENCODE_SAFE_INSTALL_DIR` - Diretório de instalação personalizado
2. `$XDG_BIN_DIR` - Caminho compatível com a especificação XDG Base Directory
3. `$HOME/bin` - Diretório binário padrão do usuário (se existir ou puder ser criado)
4. `$HOME/.opencode-safe/bin` - Fallback padrão

```bash
# Exemplos
OPENCODE_SAFE_INSTALL_DIR=/usr/local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
XDG_BIN_DIR=$HOME/.local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
```

### Agents

O OpenCode Safe inclui dois agents integrados, que você pode alternar com a tecla `Tab`.

- **build** - Padrão, agent com acesso total para trabalho de desenvolvimento
- **plan** - Agent somente leitura para análise e exploração de código
  - Nega edições de arquivos por padrão
  - Pede permissão antes de executar comandos bash
  - Ideal para explorar codebases desconhecidas ou planejar mudanças

Também há um subagent **general** para buscas complexas e tarefas em várias etapas.
Ele é usado internamente e pode ser invocado com `@general` nas mensagens.

Saiba mais sobre [agents](https://github.com/usamadar/opencode-safe#agents).

### Documentação

Para mais informações sobre como configurar o OpenCode Safe, [**veja nossa documentação**](https://github.com/usamadar/opencode-safe#readme).

### Contribuir

Se você tem interesse em contribuir com o OpenCode Safe, leia os [contributing docs](./CONTRIBUTING.md) antes de enviar um pull request.

### Construindo com OpenCode Safe

Se você estiver trabalhando em um projeto relacionado ao OpenCode Safe e estiver usando "opencode-safe" como parte do nome (por exemplo, "opencode-safe-dashboard" ou "opencode-safe-mobile"), adicione uma nota no README para deixar claro que não foi construído pela equipe do OpenCode Safe e não é afiliado a nós de nenhuma forma.

### FAQ

#### Como isso é diferente do Claude Code?

É muito parecido com o Claude Code em termos de capacidade. Aqui estão as principais diferenças:

- 100% open source
- Não está acoplado a nenhum provedor. Embora recomendemos os modelos que oferecemos pelo [OpenCode Safe](https://github.com/usamadar/opencode-safe#readme); o OpenCode Safe pode ser usado com Claude, OpenAI, Google ou até modelos locais. À medida que os modelos evoluem, as diferenças diminuem e os preços caem, então ser provider-agnostic é importante.
- Suporte a LSP pronto para uso
- Foco em TUI. O OpenCode Safe é construído por usuários de neovim e pelos criadores do [terminal.shop](https://terminal.shop); vamos levar ao limite o que é possível no terminal.
- Arquitetura cliente/servidor. Isso, por exemplo, permite executar o OpenCode Safe no seu computador enquanto você o controla remotamente por um aplicativo mobile. Isso significa que o frontend TUI é apenas um dos possíveis clientes.

---

**Junte-se à nossa comunidade** [Discord](https://github.com/usamadar/opencode-safe/discussions) | [X.com](https://github.com/usamadar/opencode-safe)
