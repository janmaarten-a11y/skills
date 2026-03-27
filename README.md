# Skills

> [!NOTE]
> A collection of skills from [@mattobee](https://github.com/mattobee/skills) and [@mikemai2awesome](https://github.com/mikemai2awesome/agent-skills).

Reusable skills for coding agents, built on the [Agent Skills](https://agentskills.io) open specification. Install the ones that match how you work.

## Installation

Install everything:

```bash
npx skills add janmaarten-a11y/skills
```

Or pick a combo that fits your project:

**Real projects** — these three reference each other and work best together:

```bash
npx skills add janmaarten-a11y/skills --skill more-css
npx skills add janmaarten-a11y/skills --skill frontend-conventions
npx skills add janmaarten-a11y/skills --skill frontend-a11y
```

**Small or personal projects** — a minimal setup:

```bash
npx skills add janmaarten-a11y/skills --skill tiny-css
npx skills add janmaarten-a11y/skills --skill frontend-a11y
```

**2010s aesthetic** — install the real projects trio plus the retro design skill:

```bash
npx skills add janmaarten-a11y/skills --skill more-css
npx skills add janmaarten-a11y/skills --skill frontend-conventions
npx skills add janmaarten-a11y/skills --skill frontend-a11y
npx skills add janmaarten-a11y/skills --skill frontend-design-2010s
```

## Available Skills

### Accessibility

#### frontend-a11y

Write minimal, accessible HTML, CSS, and JavaScript without over-engineering. Uses native browser elements instead of ARIA-hacking generic divs, component libraries, or focus-trap packages.

```bash
npx skills add janmaarten-a11y/skills --skill frontend-a11y
```

Use when:

- Writing any HTML markup
- Building web components or interactive elements (buttons, dialogs, accordions, tabs)
- Creating or reviewing forms
- Reviewing code for accessibility

Pair with `tiny-css` or `more-css` for CSS guidance, and `frontend-conventions` for naming.

#### predicting-accessibility-risks

Identifies accessibility risks in proposed features, designs, or technical plans before implementation begins. Produces a risk assessment with affected user groups, WCAG criteria, likelihood, cost to fix later, and specific mitigations.

```bash
npx skills add janmaarten-a11y/skills --skill predicting-accessibility-risks
```

Example prompts:

- "What accessibility risks should I watch for in this feature?"
- "Assess this design for accessibility problems before I build it"
- "What could go wrong for disabled users with this approach?"
- "Is there anything about this plan that will be expensive to fix for accessibility later?"

#### reviewing-accessibility

Reviews implemented UI code for WCAG Level AA compliance. Covers semantic HTML, keyboard navigation, focus management, ARIA, labels, visual contrast, and forms. For pre-implementation risk assessment, use `predicting-accessibility-risks` instead.

```bash
npx skills add janmaarten-a11y/skills --skill reviewing-accessibility
```

Example prompts:

- "Review this component for accessibility"
- "Audit this page against WCAG AA"
- "Is my form handling accessible?"
- "Check whether this dialog meets accessibility requirements"

#### fixing-accessibility-issues

Fixes accessibility issues in implemented UI code. Takes findings from audits, axe-core scans, or `reviewing-accessibility` and produces code changes, with pattern selection defaults for accessible names, focus management, ARIA, forms, contrast, headings, keyboard interaction, and live regions.

```bash
npx skills add janmaarten-a11y/skills --skill fixing-accessibility-issues
```

Example prompts:

- "Fix these accessibility issues"
- "Remediate the findings from the audit"
- "How should I fix this axe-core violation?"
- "Implement an accessible modal pattern for this dialog"

#### writing-accessibility-tests

Writes Playwright accessibility tests using a two-layer strategy: axe-core scans for broad automated coverage, plus targeted Playwright assertions for things axe cannot catch (accessible names, ARIA states, focus management, shadow DOM, multi-theme contrast).

```bash
npx skills add janmaarten-a11y/skills --skill writing-accessibility-tests
```

Example prompts:

- "Add accessibility tests for this page"
- "Write axe scans for all routes in light and dark mode"
- "What accessibility test coverage am I missing?"
- "How do I test accessible names on web components with shadow DOM?"

#### estimating-accessibility-effort

Estimates the effort required to remediate accessibility issues. Takes audit findings, axe-core results, or backlog items and produces T-shirt-sized effort estimates with rationale, dependencies, and quick wins.

```bash
npx skills add janmaarten-a11y/skills --skill estimating-accessibility-effort
```

Example prompts:

- "How much effort would it take to fix these accessibility issues?"
- "Size these audit findings for sprint planning"
- "Which of these accessibility fixes are quick wins?"
- "What dependencies exist between these accessibility issues?"

#### prioritising-accessibility-fixes

Prioritises a set of accessibility issues for remediation based on severity, user impact, and effort. Produces a scored, tiered remediation plan with batching recommendations and a concrete fix order.

```bash
npx skills add janmaarten-a11y/skills --skill prioritising-accessibility-fixes
```

Example prompts:

- "Prioritise these accessibility issues for our next sprint"
- "What should we fix first from this audit report?"
- "Triage this accessibility backlog"
- "Which accessibility fixes give the most value for the least effort?"

### CSS

#### tiny-css

Write minimal, efficient CSS for small or minimalist projects by trusting the browser instead of fighting it. For anything beyond a personal site or prototype, use `more-css` instead.

```bash
npx skills add janmaarten-a11y/skills --skill tiny-css
```

Use when:

- Working on a personal site, prototype, or simple landing page
- Setting up base styles without a build system
- Reviewing CSS for unnecessary declarations

#### more-css

The default CSS skill for real projects. Write scalable vanilla CSS using design tokens, cascade layers, BEM naming, `light-dark()` for theming, and OKLCH colors. No frameworks, no Sass.

```bash
npx skills add janmaarten-a11y/skills --skill more-css
```

Use when:

- Working on any multi-component or team project
- Setting up a design token system or theming
- Organizing CSS across many components with `@layer config, resets, components, utilities, overrides`

### Frontend

#### frontend-conventions

Establish and enforce consistent coding standards across HTML, CSS, and JavaScript — formatting, naming cases, class prefixes, acceptable abbreviations, modifier APIs (sizes, shades, hierarchy, breakpoints), and CSS property order.

```bash
npx skills add janmaarten-a11y/skills --skill frontend-conventions
```

Use when:

- Naming a new class, variable, component, or file
- Setting up a new project's coding conventions
- Choosing a prefix for a new CSS category
- Reviewing code for naming or formatting consistency

#### frontend-design-2010s

Recreate the authentic early-2010s corporate/SaaS web aesthetic — gradient headers, glossy CTA buttons, skeuomorphic icons, horizontal band layouts, and drop shadows. Produces fluid, complete pages that feel genuinely built in 2011.

```bash
npx skills add janmaarten-a11y/skills --skill frontend-design-2010s
```

Use when:

- Building a page or component with a 2010s, Web 2.0, or retro corporate web aesthetic
- Recreating the look of classic SaaS landing pages from circa 2010–2014

Requires `more-css`, `frontend-a11y`, and `frontend-conventions`.

### Storybook

#### format-storybook

Structure and organize Storybook files for scalability using battle-tested patterns from Cassondra Roberts. Covers story files, template files, controls, visual regression testing, and component documentation.

```bash
npx skills add janmaarten-a11y/skills --skill format-storybook
```

Use when:

- Creating or editing any Storybook story file
- Writing template files with Lit
- Organizing a component library
- Setting up visual regression tests with Chromatic

### General

#### designing-agent-teams

Designs, generates, and refines multi-agent coding teams with optimal model-to-role assignments. Produces team reasoning documents and agent instruction files that work across platforms.

```bash
npx skills add janmaarten-a11y/skills --skill designing-agent-teams
```

Example prompts:

- "Design an agent team for this codebase"
- "Review my agent team configuration and suggest improvements"
- "Add a security specialist to my existing agent team"
- "Which model tier should I use for my tester agent?"

#### suggesting-next-steps

Suggests prioritised next steps for a project based on git history, GitHub issues/PRs, tracking files, and project docs.

```bash
npx skills add janmaarten-a11y/skills --skill suggesting-next-steps
```

Example prompts:

- "What should I work on next?"
- "I haven't touched this project in a week — what's the state of things?"
- "What's left to do on this feature?"
- "Help me prioritise my backlog"

## License

MIT
