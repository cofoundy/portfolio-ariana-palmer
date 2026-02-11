# QA Report: Ariana Palmer

**Date:** 2026-02-11
**URL:** https://cofoundy.github.io/portfolio-ariana-palmer/
**Status:** FAIL

## Data Validation
- [x] Name matches source (Sheet: "Ariana Palmer" / Page: "Ariana Palmer")
- [x] Email matches source (Sheet: "arianapalmer18@gmail.com" / Page: "arianapalmer18@gmail.com")
- [x] LinkedIn matches source (Sheet: "ariana-palmer-30956233" / Page: same)
- [x] Title consistent with CV ("Program Coordinator & Community Development Specialist")
- [x] Companies listed match CV (EforAll NWA, Conexion de Negocios Latinos, San Judas Distributing, Jan Pro Cleaning Systems, La Prensa Libre / NWA Democrat Gazette)
- [x] Education institutions match CV (IED Barcelona, Udacity, UCAL Lima)
- [x] Dates match config source data
- [x] No hallucinated data detected

## Language Consistency (Previous Issues - NOW FIXED)
- [x] Hero says "Hello!" (was "Hola!")
- [x] Hero says "I'm Ariana Palmer" (was "Soy")
- [x] Section labels in English: About Me, Projects, Experience, Education
- [x] Footer says "All rights reserved." (was Spanish)
- [x] HTML lang="en" (was "es")
- [x] Footer nav links in English
- [x] No empty Twitter/GitHub icons in footer (was broken)

## Clean Deploy
- [x] No "Powered by" / "Made with" / "Built with" watermarks
- [x] No "Lorem ipsum" or placeholder text
- [x] No template links visible (View source, Fork this, etc.)
- [x] No "undefined" or "null" in content
- [x] No Astro branding visible (only in meta generator tag, acceptable)
- [x] No Vercel badge visible

## Issues Found

### Issue 1: MEDIUM - Escaped HTML tags visible in Education section
The education degree fields in config.ts contain `<strong>` HTML tags, but the Education
component renders them as escaped text instead of parsing the HTML.

**Visible on page:**
- "Bachelor's Degree in &lt;strong&gt;Graphic Design&lt;/strong&gt;"
- "Nanodegree in &lt;strong&gt;Digital Marketing&lt;/strong&gt;"

**Expected:** Bold text for "Graphic Design" and "Digital Marketing"
**Fix:** Either remove `<strong>` tags from config.ts education degree fields,
or use `set:html` directive in the Education.astro component for the degree field.

### Issue 2: LOW - Programming code symbols in Hero background
The hero section has an SVG pattern with programming symbols (`</>`, `=>`, `[]`, `()`,
`::`, `==`, `++`, `;`) at 0.2 opacity. Ariana Palmer is a **Program Coordinator &
Community Development Specialist**, not a developer. These code symbols are a template
artifact that does not match her professional profile.

**Visible:** Faint monospace code symbols in the hero background gradient
**Fix:** Remove the `programming-symbols` SVG pattern from Hero.astro, or replace
with profession-appropriate decorative elements.

### Issue 3: INFO - No mobile hamburger menu
The header navigation uses `hidden md:block` which hides it completely on mobile.
There is no hamburger menu. For a single-page portfolio with section anchors, this
is acceptable since users can scroll, but it reduces mobile navigation usability.

## Technical
- [x] Page loads (HTTP 200)
- [x] CSS loads (HTTP 200 - /_astro/index.DjP8OqGM.css)
- [x] Favicon loads (HTTP 200 - favicon.svg)
- [x] Profile image: N/A (template does not use profile image in hero)
- [ ] Console errors: Could not check (Chrome MCP unavailable)

## Summary
| Check | Result |
|-------|--------|
| Data accuracy | PASS |
| Anti-hallucination | PASS |
| Clean deploy | PASS |
| CSS/Assets loading | PASS |
| Rendering bugs | FAIL (escaped HTML in education) |
| Template artifacts | WARN (code symbols in hero for non-dev) |

## Evidence
- Screenshots could not be captured (Chrome MCP server unavailable)
- All validation performed via curl HTML extraction and HTTP status checks
