# HashForge Accessibility Guide

## Vision

HashForge is built with accessibility as a first-class concern. Everyone should be able to use this tool regardless of ability.

## Current Accessibility Features

### Screen Reader Support
- ✅ Semantic HTML5 (nav, section, button, input)
- ✅ ARIA labels on all inputs
- ✅ Tab navigation through all interactive elements
- ✅ Focus indicators (visible on keyboard navigation)

### Keyboard Navigation
- ✅ Tab through all controls
- ✅ Enter/Space to click buttons
- ✅ Arrow keys in some UI components
- ✅ No keyboard traps

### Visual
- ✅ WCAG AA color contrast (≥4.5:1)
- ✅ Readable font sizes (min 12px)
- ✅ Focus indicators (2px solid)
- ✅ No color-only information (icons + text)

### Mobile
- ✅ Touch-friendly tap targets (min 48×48px)
- ✅ Responsive design (works at 320px width)
- ✅ Readable on small screens

## Keyboard Shortcuts (Proposed)

Future additions for power users:

```
Ctrl + Enter     → Generate Hashes
Ctrl + Shift + C → Copy All Results
Ctrl + Shift + J → Export as JSON
Ctrl + Shift + T → Export as TXT
Ctrl + T         → Switch to Text mode
Ctrl + F         → Switch to File mode
Ctrl + B         → Switch to Batch mode
Ctrl + V         → Switch to Verify mode
Ctrl + I         → Switch to Identify mode
Ctrl + M         → Switch to Metadata mode
Ctrl + H         → Toggle History
Ctrl + 1/2/3/4   → Switch Theme
```

## Testing with Assistive Technology

### Screen Reader Testing

**macOS/iOS:**
- VoiceOver (built-in): Cmd+F5
- Keyboard: VoiceOver Web Rotor (VO+U)

**Windows:**
- NVDA (free): https://www.nvaccess.org/
- JAWS (paid): https://www.freedomscientific.com/

**Testing Steps:**
1. Enable screen reader
2. Tab through page
3. Verify all labels are announced
4. Verify focus order makes sense
5. Test form interactions (checkboxes, selects)

### Keyboard-Only Testing

1. Disconnect mouse/trackpad
2. Navigate using Tab, Shift+Tab, Arrow keys
3. Verify all features accessible
4. Check for keyboard traps
5. Verify focus visible at all times

## WCAG 2.1 Compliance

Target: **Level AA**

| Guideline | Status | Notes |
|-----------|--------|-------|
| 1.3.1 Info & Relationships | ✅ | Semantic HTML, proper nesting |
| 1.4.3 Contrast | ✅ | All text ≥4.5:1 (AA) |
| 1.4.4 Text Resize | ✅ | No fixed font-size in px |
| 2.1.1 Keyboard | ✅ | All features keyboard accessible |
| 2.4.3 Focus Order | ✅ | DOM order logical |
| 2.4.7 Focus Visible | ✅ | Clear focus indicators |
| 3.2.1 Predictable | ✅ | No unexpected context changes |
| 3.3.1 Error Prevention | ✅ | Validation feedback |
| 4.1.2 Name/Role/Value | ✅ | Proper ARIA labels |

## Issues & Improvements

If you find an accessibility issue:

1. **Report it**: Open an issue with label `accessibility`
2. **Include details**:
   - What assistive tech you're using
   - What you expected to happen
   - What actually happened
   - Steps to reproduce
3. **We'll fix it**: Accessibility issues are high priority

## Contributing Accessibility Fixes

Interested in improving accessibility?

### Areas for Contribution
1. **Keyboard shortcuts**: Implement the proposed shortcuts above
2. **Focus management**: Better focus indicators for complex interactions
3. **Error messages**: Make validation errors more descriptive
4. **Testing**: Help test with real assistive technology

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Resources

- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Accessibility by Google](https://www.a11y-101.com/)
- [Web Accessibility by MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility)

---

**Accessibility is for everyone.** Let's make HashForge better together! ♿✨
