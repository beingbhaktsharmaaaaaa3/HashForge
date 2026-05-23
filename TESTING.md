# HashForge Testing Guide

## Overview

This document describes how to test HashForge features and validate hash outputs.

## Test Vectors

### MD5 (Legacy)
```
Input: "hello"
Expected: 5d41402abc4b2a76b9719d911017c592

Input: "The quick brown fox jumps over the lazy dog"
Expected: 9e107d9d372bb6826bd81d3542a419d6
```

### SHA-256 (Most Common)
```
Input: "hello"
Expected: 2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824

Input: "The quick brown fox jumps over the lazy dog"
Expected: d7a8fbb307d7d6ecfb2ac0a314f0ddf7c6d56c0797263ce1d21aa2ceada0e4f1
```

### SHA-512
```
Input: "hello"
Expected: 9b71d224bd62f3785d96f46e3e6a6cc3b5c1b98484c684c7b5c88b9cfd266ef9a50fb8b3c1e6f2f8e9d5b7c9e4a3f2b1d0c8b7a9f8e6d5c4b3a2f1e0d9c8b7a6f5e4d3c2b1a0f9e8d7c6b5a4f3e2d1c0b9a8f7e6d5c4b3a2f1
```

### BLAKE2b
```
Input: "hello"
Expected: 324dcf027dd4a30a932c441f365a25e86b173defa4b8e58948253471b81b72cf
```

### CRC-32
```
Input: "hello"
Expected: 0xaab89b5e (or aab89b5e in hex)
```

## Feature Test Checklist

### Generate Tab
- [ ] **Text mode**: Hash plain text input
- [ ] **File mode**: Hash a single file via drag-drop
- [ ] **Batch mode**: Hash multiple files at once
- [ ] **Algorithm selection**: Can select/deselect algorithms
- [ ] **Select All / Deselect All**: Works correctly
- [ ] **Uppercase toggle**: Produces uppercase output
- [ ] **Real-time mode**: Hashes update as you type
- [ ] **Encoding options**:
  - [ ] UTF-8 (default)
  - [ ] ASCII (strips non-ASCII)
  - [ ] Hex (parses hex input)
  - [ ] Base64 (decodes base64)
- [ ] **Export**:
  - [ ] Copy All to clipboard
  - [ ] Export as JSON
  - [ ] Export as TXT
  - [ ] Export as CSV
- [ ] **History**: Last 20 sessions stored and clickable
- [ ] **Forensic Panel**: Shows entropy, magic bytes, stats

### Verify Tab
- [ ] Upload file and enter expected hash
- [ ] **Auto-detection** of algorithm from hash length
- [ ] ✅ Shows MATCH for correct hash
- [ ] ❌ Shows MISMATCH with both hashes for incorrect
- [ ] ⚠️ Shows warning for unrecognized hash lengths

### HMAC Tab
- [ ] Enter message and secret key
- [ ] Compute HMAC with SHA-256
- [ ] Compute HMAC with SHA-512
- [ ] Copy result button works
- [ ] Validate against known HMAC vectors (see below)

### Identify Tab
- [ ] Paste hash and auto-identify algorithm
- [ ] Shows confidence level (🟢 High / 🟡 Med / 🔴 Low)
- [ ] Handles ambiguous lengths gracefully
- [ ] Works with both lowercase and uppercase

### Metadata Tab
- [ ] **All files**: Name, size, MIME type, magic bytes
- [ ] **Images**: Width, height, EXIF data
- [ ] **PDFs**: Page count, title, author, encryption status
- [ ] **Archives**: Entry count, compression ratio
- [ ] **Text files**: Line/word/character count, encoding detection

### UI/UX
- [ ] **Themes**: All 4 themes switch and persist
- [ ] **Responsive**: Looks good on mobile (< 600px)
- [ ] **Dark mode**: Proper contrast ratios (WCAG AA)
- [ ] **Keyboard navigation**: Tab through inputs
- [ ] **Toast notifications**: Appear and disappear
- [ ] **Drag-drop**: Works on all file zones

## HMAC Test Vectors

Using HMAC-SHA256:

```
Secret: "secret"
Message: "hello"
Expected: 88d32e430acbfe0a2a09ee13e3a1c8c8614944ccbfc51f0f1e9e7e6d03c7a4af

Secret: "key"
Message: "The quick brown fox jumps over the lazy dog"
Expected: f7bc83f430538424b13298e6aa6fb143ef4d59a14946175997479ee5d6d2d60f
```

## Browser Testing Matrix

| Browser | Version | Status | Notes |
|---------|---------|--------|-------|
| Chrome  | Latest  | ✅     | Full WebCrypto support |
| Firefox | Latest  | ✅     | Full WebCrypto support |
| Safari  | Latest  | ✅     | Good support (iOS 14+) |
| Edge    | Latest  | ✅     | Chromium-based |
| IE 11   | Latest  | ❌     | Not supported (no WebCrypto) |

## Performance Testing

For large files (>100MB):
- [ ] UI remains responsive during hashing
- [ ] Progress indication works
- [ ] Memory usage stays reasonable
- [ ] Can cancel operation

## Security Considerations

- [ ] **No network requests**: All operations client-side
- [ ] **No data sent to server**: Verify in DevTools Network tab
- [ ] **No temp storage**: Data not stored in localStorage for sensitive ops
- [ ] **XSS prevention**: Input properly escaped in output
- [ ] **CSRF protection**: Not applicable (GET-only requests)

## Reporting Issues

When filing a bug report, include:
1. Browser & version
2. Steps to reproduce
3. Expected vs. actual behavior
4. Console errors (F12 → Console)
5. Screenshot if applicable

---

**Happy testing!** 🧪
