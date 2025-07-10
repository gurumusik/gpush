## **🎯 Apa Itu gpush?**
gpush adalah script CLI sederhana yang membantu kamu melakukan Git commit + push menggunakan standar Conventional Commits, tanpa harus mengetik panjang seperti:

`git add .`
`git commit -m "feat(auth): add login page"`
`git push origin HEAD`

Dengan **gpush**, kamu cukup jalankan:
`gpush feat auth -m "add login page"
`

## **🛠️ Cara Instalasi**
**💻 Untuk macOS & Linux**

1. Download / Buat file gpush
Misal kamu sudah punya **gpush** di folder project (seperti sekarang):

2. Jadikan executable
`chmod +x gpush`

3. Pindahkan ke **/usr/local/bin** agar bisa dipakai global
`sudo mv gpush /usr/local/bin/gpush`

4. Uji coba
`gpush --help`

Jika muncul panduan, maka berhasil 🎉

**🪟 Untuk Windows (WSL atau Git Bash)**
🔧 Jika pakai WSL:

1. Pindahkan file ke direktori **~/bin**
`mkdir -p ~/bin`
`mv gpush ~/bin/gpush`
`chmod +x ~/bin/gpush`

2. Tambahkan ke PATH
Edit **~/.bashrc** atau **~/.zshrc** dan tambahkan:
`export PATH="$HOME/bin:$PATH"`

3. Apply perubahan
`source ~/.bashrc  # atau source ~/.zshrc`

4. Coba jalankan
`gpush --help`

**🪟 Jika pakai Git Bash:**
Simpan file gpush di C:\Users\<YourUsername>\bin, lalu tambahkan folder itu ke PATH melalui Environment Variables.

## **🚀 Cara Menggunakan**
`gpush <type>[!] [scope] -m "message" [-b "breaking change"]`

**🔹 Parameter:**

| Parameter       | Required | Description                                              |
| --------------- | -------- | -------------------------------------------------------- |
| `<type>`        | ✅        | Commit type (see list below)                             |
| `[scope]`       | ❌        | Optional: area/module affected (e.g., auth, ui)          |
| `-m "message"`  | ✅        | Commit message                                           |
| `-b "breaking"` | ❌        | Description for breaking changes (if type ends with `!`) |
| `--to <branch>` | ❌        | Push to another branch (default: current branch)         |
| `--no-rebase`   | ❌        | Skip rebase before commit                                |
| `--no-pr`       | ❌        | Skip automatic PR creation                               |

## **📌 Contoh Penggunaan:**

**✅ Commit Biasa**
`gpush feat auth -m "add login form"`

**💬 Commit ini menghasilkan:**
`feat(auth): add login form`

**✅ Commit dengan BREAKING CHANGE**
`gpush feat! api -m "remove old endpoint" -b "Old endpoint no longer supported"`

**💬 Commit ini menghasilkan:**
`feat(api)!: remove old endpoint`
``
``
`BREAKING CHANGE: Old endpoint no longer supported`

**✅ Commit tanpa scope**
`gpush fix -m "resolve crash on startup"`

**💬 Output:**
`fix: resolve crash on startup`

## **🧩 Daftar Tipe Commit (Conventional Commit Types)**


| Type     | Emoji | Use Case                                 |
| -------- | ----- | ---------------------------------------- |
| feat     | ✨     | Add new feature                          |
| fix      | 🐛    | Bug fix                                  |
| docs     | 📝    | Documentation only                       |
| style    | 🎨    | Code style only (no logic)               |
| refactor | ♻️    | Refactor only                            |
| test     | ✅     | Add/update tests                         |
| chore    | 🔧    | Build tools / config changes             |
| perf     | ⚡️    | Performance improvements                 |
| ci       | 🤖    | CI/CD changes                            |
| build    | 🏗    | Changes to build system or dependencies  |
| revert   | ⏪     | Revert a commit                          |
| wip      | 🚧    | Work in progress                         |
| init     | 🎉    | Initial setup or commit                  |
| merge    | 🔀    | Merging branches                         |
| hotfix   | 🩹    | Quick production fix                     |
| temp     | 🧪    | Temporary commits (for debug or testing) |
| config   | ⚙️    | Configuration changes                    |
| update   | ⬆️    | Version/dependency updates               |
| security | 🔒    | Security patches                         |
| move     | 🚚    | Move files or logic                      |
| remove   | 🔥    | Remove features/files                    |

## **💡 Kenapa Harus gpush?**

- 🔐 Standar industri (Conventional Commits)
- 📖 Changelog bisa dibuat otomatis
- 🤝 Komit jelas dan mudah dibaca tim
- ⚙️ Cocok untuk automation (CI/CD, semantic release, dsb)

## **📦 Affected Version**
`v1.0.0 (new release)`

## **👤 Creator**
[Agrieva Xananda Pramuditha](https://github.com/agripaa) as Developer