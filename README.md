# 🔐 HashForge — Cryptographic Hash Toolkit

A powerful, fully client-side cryptographic hash toolkit that runs entirely in your browser. No server, no data uploads, no dependencies — just drop the HTML file and go.

![HashForge](https://img.shields.io/badge/HashForge-v1.0-00e5a0?style=for-the-badge&logo=shield&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
![HTML](https://img.shields.io/badge/HTML-Single%20File-orange?style=for-the-badge&logo=html5)
![No Dependencies](https://img.shields.io/badge/Dependencies-None-brightgreen?style=for-the-badge)

---

## ✨ Features

### 🔑 Hash Generation
- **8 algorithms** — MD5, SHA-1, SHA-256, SHA-384, SHA-512, SHA3-256, SHA3-512, BLAKE2b, CRC-32
- **3 input modes** — Text, Single File, Batch Files
- **Encoding options** — UTF-8, ASCII, Hex input, Base64 input
- Real-time hashing as you type
- Uppercase / lowercase toggle
- Copy individual hash or export all

### ✅ Hash Verification
- Drag & drop a file and paste an expected hash
- Auto-detects algorithm from hash length
- Clear MATCH / MISMATCH result with both hashes shown side by side

### 🔒 HMAC
- Keyed-hash message authentication
- Supports SHA-256, SHA-384, SHA-512, SHA3-256, BLAKE2b

### 🔍 Hash Identifier
- Paste any unknown hash string
- Identifies possible algorithms by length, format, and character set
- Confidence levels: **high / med / low**

### 📁 File Metadata Inspector
- **Every file:** name, size, MIME type, magic byte detection, MD5 + SHA-256 fingerprints
- **Entropy analysis** — Shannon entropy score with encrypted/compressed assessment
- **Hex dump** — first 128 bytes with ASCII sidebar
- **Byte distribution chart** — visual frequency across 16 byte-range groups
- **Images (JPEG/PNG/GIF/WebP):** dimensions, megapixels, aspect ratio, full EXIF data (camera make/model, ISO, exposure, f-number, focal length, GPS IFD, date taken, orientation…)
- **Audio/Video:** duration, video resolution
- **PDF:** version, title, author, creator app, page count, encryption flag
- **ZIP/Office archives:** entry listing, compression ratio, total uncompressed size
- **Text files:** encoding, line endings (CRLF/LF), line/word/character count

### 📤 Export
- Copy all hashes to clipboard
- Export as **JSON**, **TXT**, or **CSV**

### 🎨 Themes
- Matrix Green · Red Team · DFIR Blue · Terminal Amber

### 📜 History
- Last 20 hash sessions stored in-session, click to reload

---

## 🚀 Getting Started

### Option 1 — Just open it locally
```
1. Download HashForge_complete.html
2. Double-click to open in any modern browser
3. Done — no install, no server needed
```

### Option 2 — Host on GitHub Pages (free, public URL)
See the full guide below ↓

---

## 📖 GitHub Setup — Step by Step

### Prerequisites
- A [GitHub account](https://github.com) (free)
- Git installed on your computer — check with `git --version`
  - Download from https://git-scm.com if not installed

---

### Step 1 — Create a new repository on GitHub

1. Go to **https://github.com/new**
2. Fill in:
   - **Repository name:** `hashforge` (or any name you like)
   - **Description:** `Client-side cryptographic hash toolkit`
   - **Visibility:** Public *(required for free GitHub Pages)*
   - ✅ Check **"Add a README file"** — uncheck this if you're using this README
3. Click **"Create repository"**

---

### Step 2 — Clone the repository to your computer

Open a terminal (Command Prompt / PowerShell on Windows, Terminal on Mac/Linux):

```bash
git clone https://github.com/YOUR_USERNAME/hashforge.git
cd hashforge
```

> Replace `YOUR_USERNAME` with your actual GitHub username.

---

### Step 3 — Add your files

Copy these two files into the `hashforge/` folder you just cloned:
- `HashForge_complete.html` → rename it to **`index.html`**
- `README.md`

Your folder should look like:
```
hashforge/
├── index.html
└── README.md
```

> **Why rename to `index.html`?**  
> GitHub Pages automatically serves `index.html` as the homepage of your site.

---

### Step 4 — Commit and push to GitHub

```bash
# Stage all files
git add .

# Commit with a message
git commit -m "Initial release: HashForge cryptographic hash toolkit"

# Push to GitHub
git push origin main
```

If it asks for credentials, sign in with your GitHub username and a **Personal Access Token** (not your password).  
To create a token: GitHub → Settings → Developer settings → Personal access tokens → Generate new token → select `repo` scope.

---

### Step 5 — Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/YOUR_USERNAME/hashforge`
2. Click **Settings** (top tab)
3. Scroll down to **"Pages"** in the left sidebar
4. Under **"Branch"**, select `main` and folder `/ (root)`
5. Click **Save**

GitHub will show:
> ✅ Your site is live at `https://YOUR_USERNAME.github.io/hashforge/`

It takes **1–3 minutes** to go live. Refresh the Pages settings page to see the link appear.

---

### Step 6 — Update the tool in the future

Whenever you make changes to `index.html`:

```bash
# Inside your hashforge/ folder
git add index.html
git commit -m "describe what you changed"
git push origin main
```

GitHub Pages automatically re-deploys within ~1 minute.

---

## 🛡 Privacy & Security

- **100% client-side** — your files and text never leave your browser
- No analytics, no tracking, no external API calls
- No cookies, no local storage used
- Works fully offline after the page loads (except Google Fonts)
- All cryptographic operations use the browser's built-in **Web Crypto API** or pure-JS implementations

---

## 🧮 Supported Algorithms

| Algorithm | Output | Security | Notes |
|-----------|--------|----------|-------|
| MD5 | 128-bit | ⚠ Deprecated | Collision vulnerable — use for checksums only |
| SHA-1 | 160-bit | ⚠ Weak | Not recommended for security use |
| SHA-256 | 256-bit | ✅ Secure | Industry standard |
| SHA-384 | 384-bit | ✅ Secure | High security |
| SHA-512 | 512-bit | ✅ Secure | Maximum SHA-2 |
| SHA3-256 | 256-bit | ✅ Secure | NIST SHA-3 standard |
| SHA3-512 | 512-bit | ✅ Secure | Maximum SHA-3 |
| BLAKE2b | 256-bit | ✅ Secure | Modern, fast |
| CRC-32 | 32-bit | ⚠ Deprecated | Error-detection checksum only |

---

## 🌐 Browser Compatibility

| Browser | Supported |
|---------|-----------|
| Chrome 90+ | ✅ |
| Firefox 90+ | ✅ |
| Edge 90+ | ✅ |
| Safari 15+ | ✅ |
| Opera 80+ | ✅ |
| IE 11 | ❌ |

---

## 📁 File Structure

```
hashforge/
├── index.html      ← The entire app (single self-contained file)
└── README.md       ← This file
```

---

## 📝 License

MIT License — free to use, modify, and distribute.

---

## 🙏 Credits

Built with:
- [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API) — SHA family
- Pure-JS implementations for MD5, SHA-3, BLAKE2b, CRC-32, HMAC
- [JetBrains Mono](https://www.jetbrains.com/lp/mono/) + [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk) fonts
