# Installing the 1ClickWebsite MCP server

This is a remote server. Nothing needs to be installed or built locally.

1. Ask the user for their 1ClickWebsite API key. They can create one at https://www.1clickwebsite.ai/api-keys (requires a 1ClickWebsite account).
2. Add this entry to the MCP settings file:

```json
{
  "mcpServers": {
    "1clickwebsite": {
      "url": "https://www.1clickwebsite.ai/api/mcp",
      "headers": { "Authorization": "Bearer <API_KEY>" }
    }
  }
}
```

3. Verify the connection by calling the `check_credits` tool. It is free and returns the account's credit balance.

Before `create_site` or `create_lead_gen_batch`, confirm the details and credit cost with the user.
