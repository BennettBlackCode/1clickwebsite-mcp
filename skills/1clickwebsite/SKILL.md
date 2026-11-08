---
name: 1clickwebsite
description: Build, edit and track WordPress websites for local service businesses with 1ClickWebsite, and run Lead Gen batches of personalized demo sites. Use when the user wants to create a website for a business, edit one of their 1ClickWebsite sites, or make demo sites for a list of prospects.
---

# 1ClickWebsite

Uses the 1ClickWebsite MCP server (`https://www.1clickwebsite.ai/api/mcp`, Bearer API key from https://www.1clickwebsite.ai/api-keys).

## Build a site
1. `find_business` with the business name and city. Show the match and confirm it with the user.
2. `check_credits`, tell the user the cost, and get a yes.
3. `create_site` with the confirmed `googlePlaceId` (and a template from `list_templates` if they picked one).
4. Builds take several minutes. Poll `site_status` and give the user the link when it's ready.

## Edit a site
1. `site_guide` for the site first and follow its rules.
2. `get_tools` with `editing`, then `run_read_tool` / `run_change_tool`.
3. Edits go live at once. Each write returns a `changeSetId`; `rollback_change_set` undoes it.

## Lead Gen demo sites
1. `list_lead_gen_templates`, then `create_lead_gen_batch` with the prospect list. Confirm the credit cost first.
2. Track with `get_lead_gen_batch`, then `export_lead_gen_batch` for the demo links to use in outreach.
