# HashForge Architecture

## Overview

HashForge is a **single-file, zero-dependency** cryptographic hash toolkit. This document explains its design.

## Design Principles

1. **Single File**: Everything in one `.html` file for easy sharing
2. **Client-Side Only**: Zero network requests, all processing local
3. **No Dependencies**: Uses native Web Crypto API + pure-JS implementations
4. **Offline-First**: Works completely without internet connection
5. **Performance**: Optimized for responsiveness on large files

## Code Structure

```
index.html
├── CSS (inline)
│   ├── CSS Variables (themes)
│   ├── Global Styles
│   ├── Layout Components
│   └── Responsive Media Queries
│
├── HTML (DOM)
│   ├── Header & Navigation
│   ├── 5 Tab Panels
│   │   ├── Generate
│   │   ├── Verify
│   │   ├── HMAC
│   │   ├── Identify
│   │   └── Metadata
│   └── Toast Notification Container
│
└── JavaScript
    ├── Crypto Primitives
    │   ├── SHA-3 (Keccak)
    │   ├── BLAKE2b
    │   ├── MD5
    │   └── CRC-32
    │
    ├── Hash Engine
    │   ├── ALGOS array (metadata)
    │   ├── hashBytes() (unified interface)
    │   └── HMAC computation
    │
    ├── App State
    │   ├── selectedAlgos (Set)
    │   ├── lastResults (array)
    │   ├── appHistory (array)
    │   └── File buffers
    │
    ├── UI Logic
    │   ├── Tab switching
    │   ├── Algorithm grid rendering
    │   ├── Theme switching
    │   └── Result display
    │
    ├── File Handling
    │   ├── Drag-drop zones
    │   ├── File input handlers
    │   ├── Metadata extraction
    │   └── Format detection (magic bytes)
    │
    ├── Export Functions
    │   ├── Copy to clipboard
    │   ├── JSON export
    │   ├── TXT export
    │   └── CSV export
    │
    └── Utilities
        ├── bytesToHex()
        ├── hexToBytes()
        ├── fmtSize()
        ├── showToast()
        └── getInputBytes()
```

## Data Flow

### Hash Generation Flow

```
User Input (text/file/batch)
    ↓
getInputBytes() → Convert to Uint8Array
    ↓
Select Algorithms
    ↓
For each algorithm:
  hashBytes(algo, bytes) → Uint8Array
    ├─ MD5 → pure-JS implementation
    ├─ SHA1/SHA256/SHA384/SHA512 → WebCrypto API
    ├─ SHA3-256/SHA3-512 → pure-JS (Keccak)
    ├─ BLAKE2b → pure-JS
    └─ CRC-32 → pure-JS lookup table
    ↓
bytesToHex() → Convert to hex string
    ↓
renderResults() → Display cards
    ↓
pushHistory() → Store in history
```

### File Verification Flow

```
Load File → Uint8Array
    ↓
Enter Expected Hash
    ↓
guessAlgoByLen() → Auto-detect algorithm
    ↓
hashBytes() → Compute actual hash
    ↓
Compare strings
    ↓
Display Result (MATCH/MISMATCH)
```

## Algorithm Implementations

### Native Web Crypto (Fast)
- SHA-1, SHA-256, SHA-384, SHA-512
- Used by `crypto.subtle.digest()`
- Hardware accelerated on modern systems

### Pure JavaScript (Portable)
- **SHA-3 (Keccak)**: Sponge construction (Keccak-f permutation)
- **BLAKE2b**: Blake2 family (16-round compression)
- **MD5**: Legacy (for compatibility only)
- **CRC-32**: Lookup table based (fast, non-cryptographic)

### Performance Targets

| Algorithm | Size | Time | Notes |
|-----------|------|------|-------|
| MD5       | 10MB | <50ms | Pure JS |
| SHA-256   | 10MB | <20ms | WebCrypto |
| BLAKE2b   | 10MB | <25ms | Pure JS |
| CRC-32    | 10MB | <10ms | Lookup table |

## Theming System

```css
/* CSS Variables (at :root) */
--bg              /* Background color */
--surface         /* Card/container color */
--surface-raised  /* Elevated surface */
--border          /* Border color */
--text-primary    /* Main text */
--text-muted      /* Dimmed text */
--accent          /* Primary accent */
--accent-glow     /* Glow effect */
--danger          /* Error color */
--warning         /* Warning color */
--success         /* Success color */
```

**Themes**: Change `--accent` and derive other colors
1. **Matrix Green** (#00e5a0)
2. **Red Team** (#ff4d6a)
3. **DFIR Blue** (#4d9fff)
4. **Terminal Amber** (#ffb800)

## State Management

### Global Variables
```javascript
let selectedAlgos      // Set<string> - selected algorithms
let currentMode        // 'text' | 'file' | 'batch'
let lastResults        // Array - latest hash results
let fileBytes          // Uint8Array - current file
let vFileBytes         // Uint8Array - file to verify
let appHistory         // Array - last 20 sessions
```

### No Framework
- Vanilla JavaScript (no React, Vue, etc.)
- DOM manipulation via `querySelector`, `getElementById`
- Event listeners via `addEventListener` and `onclick`
- State updates trigger UI re-renders

## Limitations & Constraints

### Why Single File?
- **Sharing**: One file to email/share
- **Deployment**: Works with simple HTTP server
- **GitHub Pages**: Drop in repo and enable Pages
- **Simplicity**: No build process required

### Memory Constraints
- Files loaded entirely into RAM (`arrayBuffer`)
- Large files (>1GB) may crash browser
- Batch processing: Files processed sequentially
- History limited to 20 entries to save memory

### Browser Compatibility
- Requires modern browser with WebCrypto API
- IE 11 not supported
- Mobile browsers: iOS Safari 14+, Chrome Android

## Future Improvements

### Performance
- [ ] Web Workers for large file processing
- [ ] Streaming hash computation (avoid loading entire file)
- [ ] IndexedDB caching for file hashes

### Features
- [ ] Keyboard shortcuts
- [ ] Hash pattern detection (credit card, email)
- [ ] Comparison tool (hash multiple files)
- [ ] Integrity reports (JSON format)

### Code Quality
- [ ] Unit tests framework
- [ ] TypeScript for type safety
- [ ] ESLint + Prettier formatting
- [ ] Minified production build

## Contributing Guidelines

When modifying architecture:

1. **Preserve single-file design**: All code stays in index.html
2. **Keep it vanilla**: No framework dependencies
3. **Document changes**: Update this file
4. **Test thoroughly**: Cross-browser testing required
5. **Consider mobile**: Must work at <600px width

---

**Built with ❤️ for security professionals everywhere.** 🔐
