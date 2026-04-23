## Why

Sites using this Hugo theme are part of the extranix.com family but have no discoverability link back to the main site. Adding a subtle footer link increases discoverability of extranix.com from any subsite, without cluttering the UI.

## What Changes

- Append an `extranix.com` link to the footer copyright line in the theme template
- The link is shown by default for all sites using the theme
- A new config param `hide_parent_site` (boolean) allows sites to suppress the link

## Capabilities

### New Capabilities
- `parent-site-link`: A hardcoded extranix.com link appended to the footer, with a kill switch config param

### Modified Capabilities

## Impact

- `layouts/index.html`: footer section modified to append the link
- All sites using this theme will show the link by default (non-breaking — existing configs are unaffected)
