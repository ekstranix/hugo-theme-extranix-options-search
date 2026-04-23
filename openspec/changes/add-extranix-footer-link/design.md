## Context

The theme renders a footer with two configurable lines (`footer_credits_line` and `footer_copyright_line`) via Hugo params. There is currently no link to extranix.com. The footer is in `layouts/index.html` lines 164-173.

## Goals / Non-Goals

**Goals:**
- Add a subtle, hardcoded extranix.com link to the footer
- Provide a kill switch param to suppress it

**Non-Goals:**
- Making the URL or link text configurable
- Adding navigation between sibling extranix sites
- Changing footer layout or styling

## Decisions

**Append after copyright line, not as a separate `<p>`**
The link is appended inline after `footer_copyright_line` with a ` · ` separator. This keeps it subtle and avoids adding vertical space. Alternative: a third `<p>` — rejected because it's more prominent than desired.

**Hardcoded URL with `hide_parent_site` kill switch**
The link always points to `https://extranix.com` and renders by default. Sites opt out with `hide_parent_site: true`. Alternative: a configurable URL param with default — rejected as unnecessary complexity since every site using this theme is an extranix subsite.

**Hugo `not` conditional for the kill switch**
Use `{{ if not .Site.Params.hide_parent_site }}` to gate rendering. When the param is absent (default), the link shows. When set to `true`, it's hidden.

## Risks / Trade-offs

- [Non-extranix users see the link] → They can set `hide_parent_site: true`. Acceptable since this is an extranix-specific theme.
