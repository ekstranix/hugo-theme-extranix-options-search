## 1. Template Change

- [x] 1.1 Modify footer in `layouts/index.html` to append extranix.com link after `footer_copyright_line`, gated by `{{ if not .Site.Params.hide_parent_site }}`

## 2. Verify

- [x] 2.1 Confirm the link renders by default in the example site config
- [x] 2.2 Confirm setting `hide_parent_site: true` suppresses the link
