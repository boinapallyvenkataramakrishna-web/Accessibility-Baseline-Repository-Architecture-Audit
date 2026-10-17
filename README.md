# Accessibility Baseline & Repository Architecture Audit

A starter monorepo for auditing a public-service website and documenting an accessible full-stack project foundation.

> **Audit integrity:** The report template does not claim that Lighthouse or keyboard testing has already been performed. Replace all `TODO` fields with measured evidence and screenshots from your own run.

## Selected target
- National Government Services Portal: https://services.india.gov.in/
- Alternative target: replace this URL if your course specifies another website.

## Repository structure
```text
.
├── client/                 # Frontend application
├── server/                 # Backend API
├── docs/
│   ├── architecture.md
│   ├── audit-report.md
│   └── evidence/           # Screenshots and exported reports
├── tests/
│   ├── accessibility/
│   └── api/
├── .gitignore
└── README.md
```

## Audit workflow
1. Open the target website in Chrome.
2. Open DevTools → Lighthouse, select **Accessibility**, and run an audit for the target page.
3. Save the report or screenshots in `docs/evidence/`. Record the page URL, date, browser version, and score.
4. Repeat for key flows such as search or a service detail page when appropriate.
5. Test keyboard-only navigation: use Tab, Shift+Tab, Enter, Space, and Escape. Record focus order, visible focus, traps, and whether all controls work.
6. Document five evidence-backed issues in `docs/audit-report.md`. Do not report suspected issues as confirmed findings.
7. Implement a small vertical slice in the project skeleton, then add tests.

## First vertical slice (suggested)
**Service directory search**
- Client: accessible search form with a visible label, keyboard-operable submit button, results status, and empty state.
- Server: `GET /api/services?q=...` returning sample service records.
- Tests: API input validation and client accessibility checks.
- Docs: explain request/response contracts and known limitations.

## Local setup
This is a documentation-first skeleton; no application dependencies are configured yet. Choose the frontend/backend stack required by your course, then add the appropriate package manifests and setup commands. Do not advertise `npm install` or `docker compose up` as working until those files exist.

## Official resources
- Lighthouse: https://developer.chrome.com/docs/lighthouse/overview
- WCAG overview: https://www.w3.org/WAI/standards-guidelines/wcag/
- WCAG 2.2: https://www.w3.org/TR/WCAG22/
- GitHub repository setup: https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository
