<p align="center">
  <a href="https://github.com/usamadar/opencode-safe">
    <picture>
      <source srcset="packages/console/app/src/asset/logo-ornate-dark.svg" media="(prefers-color-scheme: dark)">
      <source srcset="packages/console/app/src/asset/logo-ornate-light.svg" media="(prefers-color-scheme: light)">
      <img src="packages/console/app/src/asset/logo-ornate-light.svg" alt="OpenCode Safe logo">
    </picture>
  </a>
</p>
<p align="center">เอเจนต์การเขียนโค้ดด้วย AI แบบโอเพนซอร์ส</p>
<p align="center">
  <a href="https://github.com/usamadar/opencode-safe/discussions"><img alt="Discussions" src="https://img.shields.io/github/discussions/usamadar/opencode-safe?style=flat-square" /></a>
  <a href="https://www.npmjs.com/package/opencode-safe"><img alt="npm" src="https://img.shields.io/npm/v/opencode-safe?style=flat-square" /></a>
  <a href="https://github.com/usamadar/opencode-safe/actions/workflows/publish.yml"><img alt="สถานะการสร้าง" src="https://img.shields.io/github/actions/workflow/status/usamadar/opencode-safe/publish.yml?style=flat-square&branch=dev" /></a>
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

### การติดตั้ง

```bash
# YOLO
curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash

# ตัวจัดการแพ็กเกจ
npm i -g opencode-safe@latest        # หรือ bun/pnpm/yarn
scoop install opencode-safe             # Windows
choco install opencode-safe             # Windows
brew install usamadar/tap/opencode-safe # macOS และ Linux (แนะนำ อัปเดตเสมอ)
brew install opencode-safe              # macOS และ Linux (brew formula อย่างเป็นทางการ อัปเดตน้อยกว่า)
sudo pacman -S opencode-safe            # Arch Linux (Stable)
paru -S opencode-safe-bin               # Arch Linux (Latest from AUR)
mise use -g opencode-safe               # ระบบปฏิบัติการใดก็ได้
nix run nixpkgs#opencode-safe           # หรือ github:usamadar/opencode-safe สำหรับสาขาพัฒนาล่าสุด
```

> [!TIP]
> ลบเวอร์ชันที่เก่ากว่า 0.1.x ก่อนติดตั้ง

### แอปพลิเคชันเดสก์ท็อป (เบต้า)

OpenCode Safe มีให้ใช้งานเป็นแอปพลิเคชันเดสก์ท็อป ดาวน์โหลดโดยตรงจาก [หน้ารุ่น](https://github.com/usamadar/opencode-safe/releases) หรือ [GitHub Releases](https://github.com/usamadar/opencode-safe/releases)

| แพลตฟอร์ม             | ดาวน์โหลด                             |
| --------------------- | ------------------------------------- |
| macOS (Apple Silicon) | `opencode-safe-desktop-darwin-aarch64.dmg` |
| macOS (Intel)         | `opencode-safe-desktop-darwin-x64.dmg`     |
| Windows               | `opencode-safe-desktop-windows-x64.exe`    |
| Linux                 | `.deb`, `.rpm`, หรือ AppImage         |

```bash
# macOS (Homebrew)
brew install --cask opencode-safe-desktop
# Windows (Scoop)
scoop bucket add extras; scoop install extras/opencode-safe-desktop
```

#### ไดเรกทอรีการติดตั้ง

สคริปต์การติดตั้งจะใช้ลำดับความสำคัญตามเส้นทางการติดตั้ง:

1. `$OPENCODE_SAFE_INSTALL_DIR` - ไดเรกทอรีการติดตั้งที่กำหนดเอง
2. `$XDG_BIN_DIR` - เส้นทางที่สอดคล้องกับ XDG Base Directory Specification
3. `$HOME/bin` - ไดเรกทอรีไบนารีผู้ใช้มาตรฐาน (หากมีอยู่หรือสามารถสร้างได้)
4. `$HOME/.opencode-safe/bin` - ค่าสำรองเริ่มต้น

```bash
# ตัวอย่าง
OPENCODE_SAFE_INSTALL_DIR=/usr/local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
XDG_BIN_DIR=$HOME/.local/bin curl -fsSL https://raw.githubusercontent.com/usamadar/opencode-safe/refs/heads/dev/install | bash
```

### เอเจนต์

OpenCode Safe รวมเอเจนต์ในตัวสองตัวที่คุณสามารถสลับได้ด้วยปุ่ม `Tab`

- **build** - เอเจนต์เริ่มต้น มีสิทธิ์เข้าถึงแบบเต็มสำหรับงานพัฒนา
- **plan** - เอเจนต์อ่านอย่างเดียวสำหรับการวิเคราะห์และการสำรวจโค้ด
  - ปฏิเสธการแก้ไขไฟล์โดยค่าเริ่มต้น
  - ขอสิทธิ์ก่อนเรียกใช้คำสั่ง bash
  - เหมาะสำหรับสำรวจโค้ดเบสที่ไม่คุ้นเคยหรือวางแผนการเปลี่ยนแปลง

นอกจากนี้ยังมีเอเจนต์ย่อย **general** สำหรับการค้นหาที่ซับซ้อนและงานหลายขั้นตอน
ใช้ภายในและสามารถเรียกใช้ได้โดยใช้ `@general` ในข้อความ

เรียนรู้เพิ่มเติมเกี่ยวกับ [เอเจนต์](https://github.com/usamadar/opencode-safe#agents)

### เอกสารประกอบ

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีกำหนดค่า OpenCode Safe [**ไปที่เอกสารของเรา**](https://github.com/usamadar/opencode-safe#readme)

### การมีส่วนร่วม

หากคุณสนใจที่จะมีส่วนร่วมใน OpenCode Safe โปรดอ่าน [เอกสารการมีส่วนร่วม](./CONTRIBUTING.md) ก่อนส่ง Pull Request

### การสร้างบน OpenCode Safe

หากคุณทำงานในโปรเจกต์ที่เกี่ยวข้องกับ OpenCode Safe และใช้ "opencode-safe" เป็นส่วนหนึ่งของชื่อ เช่น "opencode-safe-dashboard" หรือ "opencode-safe-mobile" โปรดเพิ่มหมายเหตุใน README ของคุณเพื่อชี้แจงว่าไม่ได้สร้างโดยทีม OpenCode Safe และไม่ได้เกี่ยวข้องกับเราในทางใด

### คำถามที่พบบ่อย

#### ต่างจาก Claude Code อย่างไร?

คล้ายกับ Claude Code มากในแง่ความสามารถ นี่คือความแตกต่างหลัก:

- โอเพนซอร์ส 100%
- ไม่ผูกมัดกับผู้ให้บริการใดๆ แม้ว่าเราจะแนะนำโมเดลที่เราจัดหาให้ผ่าน [OpenCode Safe](https://github.com/usamadar/opencode-safe#readme) OpenCode Safe สามารถใช้กับ Claude, OpenAI, Google หรือแม้กระทั่งโมเดลในเครื่องได้ เมื่อโมเดลพัฒนาช่องว่างระหว่างพวกมันจะปิดลงและราคาจะลดลง ดังนั้นการไม่ผูกมัดกับผู้ให้บริการจึงสำคัญ
- รองรับ LSP ใช้งานได้ทันทีหลังการติดตั้งโดยไม่ต้องปรับแต่งหรือเปลี่ยนแปลงฟังก์ชันการทำงานใด ๆ
- เน้นที่ TUI OpenCode Safe สร้างโดยผู้ใช้ neovim และผู้สร้าง [terminal.shop](https://terminal.shop) เราจะผลักดันขีดจำกัดของสิ่งที่เป็นไปได้ในเทอร์มินัล
- สถาปัตยกรรมไคลเอนต์/เซิร์ฟเวอร์ ตัวอย่างเช่น อาจอนุญาตให้ OpenCode Safe ทำงานบนคอมพิวเตอร์ของคุณ ในขณะที่คุณสามารถขับเคลื่อนจากระยะไกลผ่านแอปมือถือ หมายความว่า TUI frontend เป็นหนึ่งในไคลเอนต์ที่เป็นไปได้เท่านั้น

---

**ร่วมชุมชนของเรา** [Discord](https://github.com/usamadar/opencode-safe/discussions) | [X.com](https://github.com/usamadar/opencode-safe)
