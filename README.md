# 🔐 HashForge — Cryptographic Hash Toolkit

A fully client-side cryptographic hash toolkit that runs entirely in your browser. No server, no installs, no data ever leaves your device.

---

## 📌 Tool Overview

HashForge is a single HTML file that gives you a complete suite of hash tools:

- **Generate** — Hash any text or file using 8 algorithms: MD5, SHA-1, SHA-256, SHA-384, SHA-512, SHA3-256, SHA3-512, BLAKE2b, CRC-32
- **Verify** — Drop a file and paste an expected hash to check if it matches
- **HMAC** — Generate keyed message authentication codes
- **Identify** — Paste an unknown hash and find out which algorithm produced it
- **Metadata** — Inspect deep file metadata: EXIF data, entropy, hex dump, image dimensions, PDF info, ZIP contents, and more
- **Export** — Download results as JSON, TXT, or CSV
- **Themes** — 4 color themes: Matrix Green, Red Team, DFIR Blue, Terminal Amber

---

## 📦 Installation

No install required. HashForge is a single `.html` file.

**Option 1 — Run locally**

1. Download `index.html`
2. Double-click to open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. That's it — fully working offline

**Option 2 — Host on GitHub Pages (free public URL)**

1. Create a new **public** repository on [github.com/new](https://github.com/new)
2. Clone it to your computer:
   ```bash
   git clone https://github.com/YOUR_USERNAME/hashforge.git
   cd hashforge
   ```
3. Copy `index.html` and `README.md` into the folder
4. Push to GitHub:
   ```bash
   git add .
   git commit -m "Initial release"
   git push origin main
   ```
5. Go to **Settings → Pages**, set branch to `main`, folder to `/ (root)`, click **Save**
6. Your live URL will be ready in ~2 minutes:
   ```
   https://YOUR_USERNAME.github.io/hashforge/
   ```

---

## 📖 How to Use

### Generate Hashes

1. Open the **Generate** tab
2. Select one or more algorithms from the grid (click to toggle)
3. Choose an input mode:
   - **Text** — type or paste any text
   - **File** — drag & drop or browse a single file
   - **Batch** — drop multiple files to hash them all at once
4. Click **Generate Hashes**
5. Results appear below — click **Copy** next to any hash, or use the export buttons to save all results

> Enable **Real-time** in options to hash automatically as you type.

---

### Verify a File

1. Open the **Verify** tab
2. Drag & drop the file you want to check
3. Paste the expected hash in the input box
4. Click **Verify** — the tool auto-detects the algorithm from the hash length
5. You will see a clear ✅ MATCH or ❌ MISMATCH result

---

### Generate an HMAC

1. Open the **HMAC** tab
2. Enter your **message** and a **secret key**
3. Select an algorithm (SHA-256, SHA-384, SHA-512, SHA3-256, BLAKE2b)
4. Click **Compute HMAC**
5. Copy the result with the Copy button

---

### Identify an Unknown Hash

1. Open the **Identify** tab
2. Paste the hash string into the input
3. Click **Identify**
4. HashForge shows all possible matching algorithms with a confidence level (high / med / low)

---

### Inspect File Metadata

1. Open the **Metadata** tab
2. Drag & drop any file onto the drop zone
3. Results load instantly and include:
   - **Basic info** — name, size, type, last modified, MD5 + SHA-256
   - **Entropy** — randomness score (useful for detecting encrypted or compressed content)
   - **Hex dump** — first 128 bytes with ASCII sidebar
   - **Byte distribution** — visual chart of byte frequency
   - **Image files** — dimensions, megapixels, aspect ratio, full EXIF (camera, ISO, exposure, GPS, date)
   - **Audio/Video** — duration, resolution
   - **PDF** — version, author, title, page count, encryption status
   - **ZIP/Office files** — file listing, compression ratio
   - **Text files** — encoding, line endings, line/word count
