## ADDED Requirements

### Requirement: Footer displays extranix.com link
The theme footer SHALL append a link to `https://extranix.com` with text `extranix.com` after the copyright line content, separated by ` · `.

#### Scenario: Default rendering
- **WHEN** a site uses this theme without setting `hide_parent_site`
- **THEN** the footer displays ` · <a href="https://extranix.com">extranix.com</a>` after the copyright line

#### Scenario: Copyright line is empty
- **WHEN** `footer_copyright_line` is not set but `hide_parent_site` is not true
- **THEN** the footer SHALL still display the extranix.com link

### Requirement: Kill switch to hide parent site link
The theme SHALL support a `hide_parent_site` boolean config param that suppresses the extranix.com link.

#### Scenario: Kill switch enabled
- **WHEN** `hide_parent_site` is set to `true` in site params
- **THEN** the extranix.com link SHALL NOT be rendered in the footer
