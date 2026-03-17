# CLAUDE.md - Westbrook AI Website

## Project Overview
Static HTML website for Westbrook AI, deployed on Cloudflare Pages. Pure HTML/CSS/JavaScript with no build tools or frameworks.

## Language
All code, comments, commit messages, and documentation must be written in English.

## Project Structure
```
.
├── index.html           # Homepage
├── about.html          # About page
├── privacy_policy.html # Privacy policy page
├── wrangler.toml       # Cloudflare Pages config
└── .github/
    └── workflows/
        └── deploy.yml  # Auto-deployment to Cloudflare Pages
```

## Design System
- **Fonts**: DM Sans (body), Playfair Display (headings)
- **Colors**:
  - Background: `#FAFAF8`
  - Text: `#1A1A18`
  - Accent: `#2D5A3D` (green)
  - Muted: `#6B6B64`
- **Max width**: 960px for main content
- **Spacing**: rem-based, mobile-first responsive

## Development Guidelines

### HTML Standards
- Use semantic HTML5 elements
- Include proper `aria-label` and `role` attributes for accessibility
- Keep CSS inline in `<style>` tags (current pattern)
- Maintain consistent structure across pages (nav, footer)
- Support `prefers-reduced-motion` for animations

### CSS Conventions
- Use CSS custom properties (`:root` variables)
- Mobile-first responsive design with `@media` queries
- Transition/animation: smooth, performance-optimized
- Focus states: always visible with `outline`

### Accessibility Requirements
- All interactive elements must have clear focus states
- Proper ARIA labels for navigation and sections
- Semantic HTML structure (nav, section, article, footer)
- Images must have descriptive alt text
- Support for reduced motion preferences

### Version Info
- Version info is auto-injected during GitHub Actions deployment
- Empty meta tags in source: `<meta name="build-version" content="">`
- CI/CD fills: version (git hash), build date (Sydney time), branch name

## Workflow

### 1. Before Making Changes
- Create an Issue describing what needs to be changed and why
- Discuss design/content changes for approval
- Create a new branch from `main`

### 2. Making Changes
- Edit HTML files directly
- Test locally by opening HTML files in browser
- Verify responsive design (mobile, tablet, desktop)
- Check accessibility (keyboard navigation, screen reader support)
- Ensure consistent styling with existing pages

### 3. Before Committing
- Validate HTML structure
- Check all internal links work
- Verify external links open in new tabs with `rel="noopener noreferrer"`
- Test on multiple browsers (Chrome, Firefox, Safari)
- Check mobile responsiveness

### 4. Deployment
- Push to branch and create PR
- GitHub Actions will create a preview deployment on Cloudflare Pages
- Preview URL will be posted as PR comment
- Review changes on preview URL
- Merge to `main` for production deployment at westbrookai.com

## Commit Convention
- `feat:` new page or feature
- `fix:` bug fix or typo correction
- `docs:` documentation changes
- `style:` CSS/design updates
- `content:` content updates (text, images)

## Common Tasks

### Adding a New Page
1. Create `new-page.html` based on existing page structure
2. Copy `<head>` section (meta tags, fonts, styles)
3. Copy navigation and footer from existing pages
4. Add new page link to navigation in all HTML files
5. Update sitemap if exists

### Updating Styles
- Modify CSS variables in `:root` for global changes
- Keep styles consistent across all pages
- Test responsive breakpoints (640px, 768px, 1024px)
- Maintain hover/focus states for all interactive elements

### Content Updates
- Use proper heading hierarchy (h1 → h2 → h3)
- Keep line length readable (max-width constraints)
- Maintain consistent tone and voice
- Check grammar and spelling

## Do Not
- Add JavaScript frameworks or build tools (keep it simple)
- Commit directly to `main` branch
- Remove accessibility features (ARIA, semantic HTML)
- Break mobile responsive design
- Remove version info meta tags (needed for CI/CD)
- Change Cloudflare deployment configuration without testing

## Testing Checklist
Before creating a PR, verify:
- [ ] All pages load correctly
- [ ] Navigation works on all pages
- [ ] Links open correctly (internal: same tab, external: new tab)
- [ ] Responsive design works (mobile, tablet, desktop)
- [ ] No console errors
- [ ] Animations respect `prefers-reduced-motion`
- [ ] Focus states visible for keyboard navigation
- [ ] Footer email and links work
- [ ] Meta tags present (description, og tags)

## Deployment Notes
- Preview deployments created for all PRs automatically
- Production deployment on merge to `main`
- Build info (git hash, date) injected during GitHub Actions
- No manual deployment needed (fully automated)
- Cloudflare Pages serves from project root (`.`)

## Contact
For questions about Westbrook AI or this website, contact: admin@westbrookai.com
