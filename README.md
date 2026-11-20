# Curator Match MCP server

Find Steam curators by name or by the games they covered, with signs of key reselling.

Curator Match lists Steam curators, the games they posted about, and signs that a curator resells game keys. This MCP server lets an assistant look up a curator or find the curators who covered games like yours.

- Endpoint: `https://curatormatch.com/api/mcp`
- Transport: streamable HTTP
- Authentication: none for light use. Heavier automated use needs a Pro key; see https://curatormatch.com/pricing.
- Website: https://curatormatch.com
- API docs: https://curatormatch.com/docs/api

All tools are read-only.

## Tools

- `search_curators`: Find Steam curators by name. Returns up to 10 with follower counts.
- `get_curator`: One curator: followers, share of high-value followers, recent posts and warning signs (none, some or several) with the reason for each.
- `find_curators_for_games`: Curators who posted about any of one to five Steam games, ranked by overlap. Pass Steam app ids. The free view shows the top few.

## Connect

Add it as a remote MCP server in any client that supports streamable HTTP:

```json
{
  "mcpServers": {
    "curatormatch": {
      "type": "http",
      "url": "https://curatormatch.com/api/mcp"
    }
  }
}
```

Claude Code: `claude mcp add --transport http curatormatch https://curatormatch.com/api/mcp`

This repository holds only this description and the registry entry (`server.json`). The server runs at the endpoint above.
