# Product

## Register

product

## Users

Two audiences, both professional and time-pressed:

- **Internal designers and developers** across the Valtioneuvosto (Finnish Council of State) and its 12 ministries, who need one shared source of truth so every ministry site looks and behaves consistently.
- **External vendors and agencies** contracted to build or maintain ministry websites, who land on this site with zero prior context and must be able to self-serve: find a component, copy its spec/markup, and ship something compliant without a briefing call.

The job to be done: look up the correct token, component spec, or accessibility rule fast, trust it's authoritative, and implement it correctly the first time.

## Product Purpose

`index.html` is the living documentation/style-guide site that renders `design.md`, the official shared design system for the Valtioneuvosto and its ministries' web communications. It is the reference tool — not a marketing site, not a template gallery — that designers, developers, and external vendors consult to build consistent, accessible government websites.

Success looks like: a vendor who has never worked with the Finnish government before can open this site, find what they need (color tokens, component anatomy, accessibility requirements, navigation patterns), and implement it correctly without follow-up questions.

## Brand Personality

Official, calm, expert-confident. Straightforward, no-nonsense, in service to clarity rather than to visual flair. No unnecessary visual effects — restraint is itself part of the credibility signal. Microcopy is plain, neutral, and solution-focused (per design.md §1.1): never blames the user, always says what to do next.

## Anti-references

- Generic consumer SaaS/startup aesthetics (gradients, glassmorphism, playful illustration) — this is a government reference tool, not a product marketing site.
- Other EU/Nordic government sites that get this wrong: cluttered, inconsistent across agencies, dated chrome, bureaucratic density that obscures rather than clarifies. The whole point of this system is to avoid that fragmentation.

## Design Principles

1. **External vendors are the hard case — design for zero-context.** If an outside agency can't self-serve a correct implementation from this site alone, the documentation has failed its primary job.
2. **Accessibility is the floor, not a feature.** WCAG 2.1 AA compliance is non-negotiable across every component and example shown; this is a legal requirement (digipalvelulaki), not a nice-to-have.
3. **Restraint signals authority.** Calm, official, expert-confident — visual effects are justified only when they serve clarity, never decoration for its own sake.
4. **One source of truth, twelve ministries.** Every spec shown must hold up as the single shared answer across all ministry sites; document the rule once, precisely, rather than leaving room for per-ministry interpretation.
5. **Show, don't just tell.** Where possible, live-rendered examples (not just prose specs) reduce misimplementation risk for vendors unfamiliar with the system.

## Accessibility & Inclusion

WCAG 2.1 A/AA compliance is mandatory (digipalvelulaki), with WCAG 2.2 refinements anticipated. Detailed, already-codified requirements live in `design.md` §2 and are binding for any new work on this site:

- Full keyboard operability; every interactive element has a visible focus indicator (≥3px, ≥3:1 contrast).
- Minimum touch target size 44×44px.
- Minimum text contrast 4.5:1; color is never the sole carrier of information.
- Animations subtle (max `0.2s ease-in-out`) and fully suppressed under `prefers-reduced-motion`.
- Semantic landmarks (`nav`, `main`, `header`, `footer`), unique `aria-label`s per navigation region, visually-hidden skip link.
- `sr-only` (not `display:none`/`visibility:hidden`) for screen-reader-only text.
- Auto-opening elements (cookie banners, service notices) placed above the header, pushing content down rather than overlaying it; never blocking site use before the user responds.
- Plain, neutral, blame-free microcopy (selkokieli-aligned), especially in error states.
