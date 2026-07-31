---
applyTo: "src/static/**/*,*.html,*.css,*.js"
---

# Frontend-Specific Guidelines

## Accessibility
- Use semantic HTML elements where possible.
- Ensure sufficient color contrast and keyboard navigability.
- Add accessible labels/text for interactive elements.

## UX Consistency
- Keep layout and spacing consistent with existing pages.
- Reuse existing styles/components before creating new ones.
- Keep user-facing messages clear and concise.

## Performance
- Prefer lightweight DOM updates over full re-renders.
- Minimize blocking scripts and avoid unnecessary dependencies.
- Optimize images/assets and avoid duplicate CSS rules.

## Error Handling
- Show clear, actionable error states to users.
- Avoid silent failures in client-side logic.
- Log unexpected client errors in a debuggable way.
