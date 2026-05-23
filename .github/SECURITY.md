# Security Policy

## Overview

HashForge is designed with **security-first** principles:

- ✅ **100% Client-Side**: All processing happens in your browser
- ✅ **No Network Requests**: Nothing is sent anywhere
- ✅ **Open Source**: Full code transparency
- ✅ **Auditable**: Pure JavaScript (not minified by default)

## What HashForge Does NOT Do

- ❌ Send your files/hashes anywhere
- ❌ Store data on servers
- ❌ Use any external APIs
- ❌ Track your activity
- ❌ Require authentication
- ❌ Load external scripts

## Algorithm Security Levels

### ✅ Secure (Use These)
- **SHA-256**: Industry standard, NIST approved
- **SHA-384**: High-security variant of SHA-2
- **SHA-512**: Maximum SHA-2 strength
- **SHA3-256**: Modern NIST SHA-3 standard
- **SHA3-512**: Maximum SHA-3 strength
- **BLAKE2b**: Modern, cryptographically secure, faster than MD5

### ⚠️ Weak (Legacy Only)
- **SHA-1**: Collision attacks exist, avoid for security-critical use
- **MD5**: Cryptographically broken, only for backward compatibility

### 🔴 Deprecated (Do Not Use)
- **CRC-32**: Not cryptographic, error-detection only

## Reporting Security Issues

**DO NOT** open a public GitHub issue for security vulnerabilities.

Instead, please email: `security@yourcontact.com`

Include:
1. Description of vulnerability
2. Steps to reproduce
3. Potential impact
4. Suggested fix (if you have one)

We will:
- Acknowledge receipt within 48 hours
- Investigate and confirm the issue
- Release a fix and credit you (unless you prefer anonymity)
- Publish a security advisory

## Best Practices for Using HashForge

### For File Integrity Verification
1. ✅ Download HashForge offline
2. ✅ Disconnect from internet
3. ✅ Verify the file hash
4. ✅ Compare against official source (via secure channel)
5. ✅ Delete sensitive files after verification

### For Password Hashing
⚠️ **DO NOT use this tool** for password hashing!

HashForge hashes are **not salted** or **key-derived**. Use proper password hashing algorithms:
- bcrypt
- Argon2
- PBKDF2 with high iteration count

### For HMAC
✅ Safe for:
- API authentication
- Message authentication
- Integrity verification

❌ NOT safe for:
- Password hashing
- Key derivation

## How to Verify HashForge Integrity

Before using this tool, verify the download:

```bash
# Download index.html
wget https://github.com/beingbhaktsharmaaaaaa3/HashForge/raw/main/index.html

# Compute SHA-256
sha256sum index.html

# Compare with published hash on GitHub Releases
```

## Code Auditing

HashForge is designed to be auditable:

1. **Full Source**: No minification (production build available)
2. **Single File**: All code in one place, easy to review
3. **No Dependencies**: No hidden code from packages
4. **Pure JS**: Can be read and understood
5. **Comments**: Complex crypto functions documented

### Audit Checklist
- [ ] No `eval()` or `Function()` calls
- [ ] No external script loading
- [ ] No network requests
- [ ] No localStorage/sessionStorage for sensitive data
- [ ] No Service Worker installing
- [ ] All crypto from trusted sources

## Known Limitations

1. **File Size**: Browser RAM limit (~2GB on desktop, less on mobile)
2. **Algorithm Selection**: Pure-JS implementations slower than native
3. **History**: Limited to 20 entries to save memory
4. **EXIF Data**: May expose personal information (location, dates)
   - Review extracted EXIF before sharing hashes

## Cryptographic Libraries

HashForge uses:
- **Web Crypto API**: Native SHA-1, SHA-256, SHA-384, SHA-512
- **Pure-JS SHA-3**: Reference Keccak implementation
- **Pure-JS BLAKE2b**: Reference Blake2 implementation
- **Pure-JS MD5**: Legacy implementation (do not use for security)
- **CRC-32**: Lookup table based (non-cryptographic)

All implementations validated against test vectors.

## Compliance

- ✅ No GDPR violations (no data collection)
- ✅ No CCPA restrictions (no personal data)
- ✅ Compatible with HIPAA (client-side processing)
- ✅ Compatible with SOC 2 (no data transmission)

---

**Use HashForge responsibly.** 🔐
