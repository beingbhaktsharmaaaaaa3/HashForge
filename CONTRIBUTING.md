# Contributing to HashForge

Thank you for wanting to improve HashForge! This guide will help you get started.

## Getting Started

1. **Fork & Clone**
   ```bash
   git clone https://github.com/YOUR_USERNAME/HashForge.git
   cd HashForge
   ```

2. **Development**
   - Open `index.html` directly in your browser
   - Make changes and reload
   - No build process required!

## Code Style

- Use **ES6+ syntax** (const/let, arrow functions)
- Keep functions **under 50 lines** when possible
- Use **meaningful variable names** (avoid `a`, `b`, `x` except in loops)
- Comment complex logic, especially in crypto functions
- Use **camelCase** for variables/functions, **UPPER_SNAKE_CASE** for constants

## Making Changes

### Bug Fixes
1. Open an issue first (if one doesn't exist)
2. Reference the issue in your PR
3. Add a test case if applicable

### New Features
1. Discuss in an issue first
2. Keep the tool **single-file** by design
3. Ensure it works **offline & client-side only**
4. Test on mobile (< 600px width)

### Adding Algorithms

To add a new hash algorithm:

1. Implement the crypto function (or use a reference implementation)
2. Add entry to `ALGOS` array:
   ```javascript
   {
     id: 'SHA3-512',
     name: 'SHA3-512',
     bits: 512,
     security: 'ok',
     note: 'Maximum SHA-3'
   }
   ```
3. Update `hashBytes()` function to handle the new algorithm
4. Update README with algorithm table
5. Test against known vectors

## Testing

### Manual Testing Checklist
- [ ] Generate hashes on text/file/batch modes
- [ ] Verify a file with correct hash (should ✓ MATCH)
- [ ] Verify a file with wrong hash (should ✗ MISMATCH)
- [ ] Test HMAC with various algorithms
- [ ] Identify hashes (test all bit lengths)
- [ ] Check metadata extraction (images, PDFs, archives)
- [ ] Test all 4 themes
- [ ] Test on mobile (portrait & landscape)
- [ ] Export as JSON/TXT/CSV
- [ ] Check browser console for errors

### Automated Testing
When contributing significant logic, please add test cases:
```javascript
// Example: test vectors for MD5
const testVectors = [
  { input: '', expected: 'd41d8cd98f00b204e9800998ecf8427e' },
  { input: 'hello', expected: '5d41402abc4b2a76b9719d911017c592' }
];
```

## Submitting a PR

1. **Branch naming**: `fix/issue-name` or `feature/description`
2. **Commit messages**: Use imperative mood
   - ✅ "Add SHA3-512 support"
   - ❌ "Added SHA3-512 support"
3. **PR title**: Describe the change clearly
4. **PR description**: Explain the why, not just what
5. **Test on multiple browsers** (Chrome, Firefox, Safari, Edge)

## Code Review

- Be respectful and constructive
- Ask questions if something is unclear
- Suggest improvements, don't demand them
- Thank reviewers for their feedback!

## Questions?

Open an issue with the `question` label. No question is too small!

---

**Happy contributing! 🚀**
