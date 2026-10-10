<div align="center">

  # Mnet Auto Reg

  **Automatically register Mnet Plus accounts. Choose the count, the tool does the rest.**

  [![Go](https://img.shields.io/badge/Go-1.22-00ADD8?logo=go&logoColor=white)](https://go.dev)
  [![Windows](https://img.shields.io/badge/Windows-amd64/arm64-0078D4?logo=windows&logoColor=white)](https://github.com/yngpiu/mnet-auto-reg/releases)
  [![Linux](https://img.shields.io/badge/Linux-amd64/arm64-FCC624?logo=linux&logoColor=black)](https://github.com/yngpiu/mnet-auto-reg/releases)
  [![macOS](https://img.shields.io/badge/macOS-amd64/arm64-000000?logo=apple&logoColor=white)](https://github.com/yngpiu/mnet-auto-reg/releases)
</div>

---

## ✨ Features

- 🤖 **Auto Mode**: Auto temp email + API registration with 3 retries and domain rotation + blacklist.
- ✍️ **Manual Mode**: Bring your own email + API registration.
- 👤 **Human-like Behavior**: Random delays between accounts to avoid rate limiting — slow by design.
- 🔑 **Password Management**: Change the default password from the menu (8–20 chars, uppercase + lowercase + number + special char).
- 🔄 **Mode Switching**: Toggle between Auto and Manual anytime from the menu or via `config.json`.
- 💾 **Auto-Save**: All created accounts are appended to `accounts.txt` with timestamped session headers.

## 🛠️ Tech Stack

- **Language**: [Go](https://go.dev/) (standard library only, zero external dependencies)
- **Architecture**: Single-package CLI (`package main`), interactive menu loop
- **Config**: Auto-created `config.json` next to the binary (stores `password`, `mode`)
- **Distribution**: Pre-built binaries for Windows, Linux, and macOS (amd64 + arm64) via GitHub Releases

## 🚀 Getting Started

### Prerequisites

- [Go](https://go.dev/dl/) (v1.22+) — only needed to build from source. Pre-built binaries need nothing.

### Installation

1. Download the pre-built binary (recommended) from [releases](https://github.com/yngpiu/mnet-auto-reg/releases):

| File | Platform | Arch |
|---|---|---|
| `mnet-auto-x64.exe` | Windows | amd64 |
| `mnet-auto-arm64.exe` | Windows | arm64 |
| `mnet-auto-x64.bin` | Linux | amd64 |
| `mnet-auto-arm64.bin` | Linux | arm64 |
| `mnet-auto-macos-x64` | macOS | amd64 |
| `mnet-auto-macos-arm64` | macOS | arm64 |

2. Or build from source:
```bash
git clone https://github.com/yngpiu/mnet-auto-reg.git
cd mnet-auto-reg
go build -o mnet-auto.exe .
```

3. Run the tool:
```bash
.\mnet-auto.exe
```
The interactive menu will appear:
```
Mnet Plus Account Auto Registration

  Current password: nmixx0222-
  Current mode: Auto

  1. Create Account
  2. Switch Mode
  3. Change Password
  4. Exit
```

## 🌐 Configuration

No environment variables needed. Configuration is persisted in `config.json`, auto-created next to the binary on first run:

```json
{
  "password": "nmixx0222-",
  "mode": "auto"
}
```

- Change the default password before creating accounts (requirements: 8–20 chars, uppercase + lowercase + number + special char).
- Switch `mode` between `auto` and `manual` anytime from the menu.

## 📦 Notes

- Random delay between accounts to avoid rate limiting.
- Accounts are saved to `accounts.txt` in the same folder as the binary.
- Emails are temporary — save them if you need them later.

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
