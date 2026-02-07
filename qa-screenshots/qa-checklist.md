# QA Report: Ariana Palmer

**Date:** 2026-02-06
**URL:** https://cofoundy.github.io/portfolio-ariana-palmer/
**Status:** FAIL

## Data Validation
- [x] Name matches source (Sheet: "Ariana Palmer" / Site: "Ariana Palmer")
- [x] Email matches sheet (`arianapalmer18@gmail.com`)
- [x] Job title reasonable ("Program Coordinator & Community Development Specialist")
- [x] Companies listed appear legitimate (EforAll NWA, CNL, San Judas Distributing, Jan Pro, La Prensa Libre)
- [x] Education institutions listed (IED Barcelona, Udacity, UCAL Lima)
- [x] No hallucinated data detected

## Clean Deploy
- [x] No watermarks (no "Powered by", "Made with", etc.)
- [x] No placeholder text
- [x] No template links

## Technical
- [x] Page loads (HTTP 200)
- [x] CSS loads (HTTP 200 - `_astro/index.z47Fn8Iq.css`)
- [x] Favicon loads (HTTP 200 - `favicon.svg`)
- [x] No profile image on site (client did upload a photo but it was not included)
- [x] No critical console errors

## Language
- [ ] **FAIL**: Content is in English but nav items are in Spanish ("Sobre Mi", "Proyectos", "Experiencia", "Educacion")
- [ ] **FAIL**: html lang="es" but all content is in English

## Issues Found
1. **FAIL - Language inconsistency**: Nav/section headers are in Spanish ("Sobre Mi", "Proyectos", "Experiencia", "Educacion") but ALL content is in English. The html lang attribute is "es" but should be "en".
2. **NOTE - No profile photo**: Client uploaded a photo in the form but it was not included on the site.
3. **NOTE - Screenshot capture failed**: Chrome screenshot tool timed out repeatedly for this page. Visual verification was done via web content extraction only.

## Evidence
- (screenshot could not be captured due to Chrome MCP timeout)
