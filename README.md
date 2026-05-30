<div align="center">

<img src="https://img.shields.io/badge/%F0%9F%94%90-HashForge-00e5a0?style=for-the-badge&labelColor=0a0a0f&color=00e5a0" height="42"/>

# HashForge — Cryptographic Hash Toolkit

**A powerful, fully client-side cryptographic hash toolkit.**  
Hash, verify, identify, HMAC, and inspect file metadata — all in a single HTML file, right in your browser.

<br/>

[![Live Demo](https://img.shields.io/badge/▶%20Live%20Demo-GitHub%20Pages-00e5a0?style=for-the-badge&labelColor=0a0a0f)](https://YOUR_USERNAME.github.io/hashforge/)
[![Single File](https://img.shields.io/badge/Single%20File-No%20Install-blueviolet?style=for-the-badge&labelColor=0a0a0f)](./index.html)
[![Client Side](https://img.shields.io/badge/100%25-Client%20Side-ff4d6a?style=for-the-badge&labelColor=0a0a0f)](#-security)
[![Tests](https://img.shields.io/badge/Tests-Automated-4d9fff?style=for-the-badge&labelColor=0a0a0f)](https://github.com/beingbhaktsharmaaaaaa3/HashForge/actions)
[![License](https://img.shields.io/badge/License-MIT-ffb800?style=for-the-badge&labelColor=0a0a0f)](#-license)

<br/>

```
  ██╗  ██╗ █████╗ ███████╗██╗  ██╗███████╗ ██████╗ ██████╗  ██████╗ ██████╓─
  ██║  ██║██╔══██╗██╔════╝██║  ██║██╔════╝██╔═══██╗██╔══██╗██╔════╝ ██╔══██╗
  ███████║███████║███████╗███████║█████╗  ██║   ██║██████╔╝██║  ███╗███████║
  ██╔══██║██╔══██║╚════██║██╔══██║██╔══╝  ██║   ██║██╔══██╗██║   ██║██╔═══╝
  ██║  ██║██║  ██║███████║██║  ██║██║     ╚██████╔╝██║  ██║╚██████╔╝███████╗
  ╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝╚═╝      ╚═════╝ ╚═╝  ╚═╝ ╚═════╝ ╚══════╝
```

</div>

---

## 🗂 Table of Contents

- [Overview](#-overview)
- [Features at a Glance](#-features-at-a-glance)
- [Supported Algorithms](#-supported-algorithms)
- [Installation](#-installation)
- [How to Use](#-how-to-use)
  - [Generate Hashes](#-generate-hashes)
  - [Verify a File](#-verify-a-file)
  - [HMAC](#-hmac)
  - [Identify a Hash](#-identify-a-hash)
  - [File Metadata](#-file-metadata)
- [Themes](#-themes)
- [Documentation](#-documentation)
- [Security](#-security)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🔭 Overview

> **HashForge** is an all-in-one cryptographic toolkit bundled as a **single `.html` file**.  
> Open it locally or deploy it to GitHub Pages — no server, no backend, no dependencies.  
> Everything runs in your browser using the native **Web Crypto API** and pure-JS implementations.

```
Your files and text never leave your device. Ever.
```

----------------------------------------

## ⚡ Features at a Glance

| Feature | Description |
|---------|-------------|
| 🔑 **Hash Generator** | Hash text, a file, or batch-hash multiple files at once |
| ✅ **Hash Verifier** | Verify file integrity against a known hash — auto-detects algorithm |
| 🔒 **HMAC** | Keyed-hash message authentication with 5 algorithm choices |
| 🔍 **Hash Identifier** | Paste any unknown hash and identify the likely algorithm |
| 📁 **Metadata Inspector** | Deep file analysis — EXIF, entropy, hex dump, ZIP contents, PDF info |
| 📤 **Export** | Copy all, or download as JSON / TXT / CSV |
| 🎨 **4 Themes** | Matrix Green · Red Team · DFIR Blue · Terminal Amber |
| 📜 **History** | Last 20 hash sessions stored in-memory, click to reload |
| ♿ **Accessible** | WCAG AA compliant with keyboard navigation and screen reader support |

---

## 🧮 Supported Algorithms

| # | Algorithm | Output | Security | Use Case |
|---|-----------|--------|----------|----------|
| 1 | `MD5` | 128-bit | ⚠️ Deprecated | Legacy checksums only |
| 2 | `SHA-1` | 160-bit | ⚠️ Weak | Avoid for security use |
| 3 | `SHA-256` | 256-bit | ✅ Secure | Industry standard |
| 4 | `SHA-384` | 384-bit | ✅ Secure | High-security applications |
| 5 | `SHA-512` | 512-bit | ✅ Secure | Maximum SHA-2 strength |
| 6 | `SHA3-256` | 256-bit | ✅ Secure | NIST SHA-3 standard |
| 7 | `SHA3-512` | 512-bit | ✅ Secure | Maximum SHA-3 strength |
| 8 | `BLAKE2b` | 256-bit | ✅ Secure | Modern, fast, secure |
| 9 | `CRC-32` | 32-bit | ⚠️ Deprecated | Error-detection only |

-------------------------------------------

## 📦 Installation

### ▶ Option 1 — Run Locally (Instant)

No setup at all. Works offline.

```bash
1.  Download index.html
2.  Double-click it to open in Chrome, Firefox, Edge, or Safari
3.  Start hashing
```

---------------------------------------------

### 🌐 Option 2 — Host on GitHub Pages (Free Public URL)

Get a shareable link like `https://YOUR_USERNAME.github.io/hashforge/`

**Step 1 — Create a GitHub repository**

Go to **[github.com/new](https://github.com/new)** and fill in:

```
Repository name : hashforge
Visibility      : ✅ Public   (required for free Pages)
README          : skip — you already have one
```

Click **Create repository**.

---

**Step 2 — Clone it to your computer**

```bash
git clone https://github.com/YOUR_USERNAME/hashforge.git
cd hashforge
```

> Replace `YOUR_USERNAME` with your actual GitHub username.

---

**Step 3 — Add your files**

Copy these two files into the `hashforge/` folder:

```
hashforge/
├── index.html      ← rename HashForge_complete.html to this
└── README.md
```

> ⚠️ The file **must** be named `index.html` — GitHub Pages serves it as the homepage automatically.

---

**Step 4 — Push to GitHub**

```bash
git add .
git commit -m "🚀 Initial release: HashForge"
git push origin main
```

If prompted for credentials, use your GitHub username and a **Personal Access Token**:
> GitHub → Settings → Developer Settings → Personal Access Tokens → Generate new token → select `repo` scope

---

**Step 5 — Enable GitHub Pages**

```
Your repo on GitHub
  → Settings (top tab)
    → Pages (left sidebar)
      → Branch: main  /  Folder: / (root)
        → Save
```

---

**Step 6 — Your site is live ✅**

Wait ~2 minutes, then visit:

```
https://YOUR_USERNAME.github.io/hashforge/
```

---

**Updating in the future**

```bash
# After editing index.html
git add index.html
git commit -m "update: describe your change"
git push origin main
# GitHub Pages auto-redeploys in ~1 minute
```

---

## 📖 How to Use

### 🔑 Generate Hashes

<details>
<summary><b>Click to expand</b></summary>

<br/>

1. Open the **Generate** tab
2. Click algorithm cards to select/deselect (multiple allowed)
3. Use **Select All** / **Deselect All** for quick picks
4. Choose your input mode:
   | Mode | When to use |
   |------|------------|
   | **Text** | Type or paste any string |
   | **File** | Drag & drop or browse a single file |
   | **Batch** | Drop multiple files — hashes all at once in a table |
5. (Optional) Set encoding: **UTF-8 / ASCII / Hex / Base64**
6. (Optional) Toggle **Uppercase** output or **Real-time** mode
7. Click **Generate Hashes**
8. Each result card shows: hash value, bit length, security status
9. Click **Copy** to copy a single hash, or **Base64** for base64-encoded output
10. Use **Export** buttons to download all results as JSON / TXT / CSV

</details>

---

### ✅ Verify a File

<details>
<summary><b>Click to expand</b></summary>

<br/>

1. Open the **Verify** tab
2. Drag & drop your file onto the drop zone (or click to browse)
3. Paste the **expected hash** in the input field
4. Click **Verify**
5. HashForge auto-detects the algorithm from the hash length:
   | Hash Length | Algorithm |
   |-------------|-----------|
   | 8 chars | CRC-32 |
   | 32 chars | MD5 |
   | 40 chars | SHA-1 |
   | 64 chars | SHA-256 |
   | 96 chars | SHA-384 |
   | 128 chars | SHA-512 |
6. Result is shown as:
   - ✅ `MATCH` — file is intact
   - ❌ `MISMATCH` — file may be corrupted or tampered; both hashes shown for comparison

</details>

---

### 🔒 HMAC

<details>
<summary><b>Click to expand</b></summary>

<br/>

1. Open the **HMAC** tab
2. Enter your **Message** (the data to authenticate)
3. Enter your **Secret Key**
4. Pick an algorithm: `SHA-256` · `SHA-384` · `SHA-512` · `SHA3-256` · `BLAKE2b`
5. Click **Compute HMAC**
6. Copy the result with the **Copy** button

> HMAC is used to verify both the integrity and authenticity of a message using a shared secret.

</details>

---

### 🔍 Identify a Hash

<details>
<summary><b>Click to expand</b></summary>

<br/>

1. Open the **Identify** tab
2. Paste any hash string into the text area
3. Click **Identify**
4. HashForge analyses the length, character set, and format and returns all possible matches with confidence levels:
   - 🟢 **High** — only one algorithm matches this exact length
   - 🟡 **Med** — multiple algorithms share this length
   - 🔴 **Low** — format is ambiguous (e.g. looks like Base64)

</details>

---

### 📁 File Metadata

<details>
<summary><b>Click to expand</b></summary>

<br/>

1. Open the **Metadata** tab
2. Drag & drop any file onto the drop zone
3. Results load instantly — what you see depends on the file type:

**Every file:**
- Name, size, MIME type, magic byte detection
- MD5 + SHA-256 fingerprints
- Shannon entropy with plain-language assessment
- Hex dump (first 128 bytes) with ASCII sidebar
- Byte frequency distribution chart

**Images (JPEG · PNG · GIF · WebP · BMP):**
- Width × Height, megapixels, aspect ratio (e.g. 16:9)
- Live preview thumbnail
- Full EXIF: camera make/model, ISO, shutter speed, f-number, focal length, GPS IFD, date/time original, orientation, flash, metering mode, color space

**Audio / Video (MP3 · MP4 · WAV · WebM · MOV):**
- Duration, media type, video resolution

**PDF:**
- PDF version, title, author, creator app, producer, creation/modified dates, page count, encryption flag

**ZIP / Office (DOCX · XLSX · PPTX · APK · EPUB):**
- Entry count, file listing (first 10), total uncompressed size, compression ratio

**Text files (TXT · JS · Python · CSV · JSON · HTML…):**
- Detected encoding (ASCII / UTF-8 / UTF-8 BOM)
- Line endings: CRLF (Windows) / LF (Unix) / Mixed
- Line count, word count, character count, longest line length

</details>

---

## 🎨 Themes

Switch themes from the top-right corner of the toolbar:

| Theme | Accent Color | Best For |
|-------|-------------|----------|
| **Matrix Green** | `#00e5a0` | Default dark hacker aesthetic |
| **Red Team** | `#ff4d6a` | Offensive security / CTF use |
| **DFIR Blue** | `#4d9fff` | Digital forensics / incident response |
| **Terminal Amber** | `#ffb800` | Classic terminal look |

---

## 📚 Documentation

HashForge includes comprehensive documentation to help you get started and contribute:

| Document | Purpose |
|----------|---------|
| [**CONTRIBUTING.md**](./CONTRIBUTING.md) | How to contribute code, report bugs, and suggest features |
| [**TESTING.md**](./TESTING.md) | Test vectors, testing checklist, and quality assurance |
| [**ARCHITECTURE.md**](./ARCHITECTURE.md) | Code structure, design patterns, and technical overview |
| [**ACCESSIBILITY.md**](./ACCESSIBILITY.md) | WCAG AA compliance, keyboard shortcuts, and assistive tech support |
| [**.github/SECURITY.md**](./.github/SECURITY.md) | Security policy, vulnerability reporting, and best practices |
| [**CHANGELOG.md**](./CHANGELOG.md) | Version history and feature changes |

### Quick Start for Developers

1. **Read**: [CONTRIBUTING.md](./CONTRIBUTING.md) — How to get started
2. **Understand**: [ARCHITECTURE.md](./ARCHITECTURE.md) — Code structure
3. **Verify**: [TESTING.md](./TESTING.md) — Test your changes
4. **Deploy**: GitHub Actions validates every push automatically ✅

---

## 🔐 Security

✅ **100% Client-Side** — No servers, no network requests  
✅ **Open Source** — Full code transparency  
✅ **Privacy-First** — Your files never leave your device  
✅ **Auditable** — Pure JavaScript, easy to review  
✅ **Automated Tests** — CI/CD pipeline validates every push  

For detailed security information, see [.github/SECURITY.md](./.github/SECURITY.md)

### Algorithm Security Levels

- ✅ **Recommended**: SHA-256, SHA-384, SHA-512, SHA3-256, SHA3-512, BLAKE2b
- ⚠️ **Legacy**: SHA-1, MD5 (only for compatibility)
- 🔴 **Non-Cryptographic**: CRC-32 (checksums only)

---

## 🤝 Contributing

We welcome contributions! Whether you want to:

- 🐛 **Report bugs** → Open an [issue](https://github.com/beingbhaktsharmaaaaaa3/HashForge/issues)
- 💡 **Suggest features** → Start a [discussion](https://github.com/beingbhaktsharmaaaaaa3/HashForge/discussions)
- 🔧 **Fix issues** → Submit a [pull request](https://github.com/beingbhaktsharmaaaaaa3/HashForge/pulls)
- 📖 **Improve docs** → Edit any `.md` file
- ♿ **Improve accessibility** → Test with screen readers
- 🧪 **Add tests** → Contribute test vectors

See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines.

### Development Setup

```bash
# Clone the repo
git clone https://github.com/beingbhaktsharmaaaaaa3/HashForge.git
cd HashForge

# Open in your browser
open index.html

# Make changes and test locally
# No build process needed!
```

---

## 📄 License

```
MIT License

Copyright (c) 2025 HashForge Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

<div align="center">

**🔐 Your cryptography, your browser, your control.**

Made with ❤️ by the HashForge Community · [MIT Licensed](./LICENSE)

</div>
