# Local Bridge Contract

The public site intentionally does not execute local processes. A small authenticated companion service on the user's machine can expose only the minimum control surface needed by the UI.

## Suggested endpoint

Base URL: `http://127.0.0.1:8765`

### `GET /status`

Return JSON similar to:

```json
{
  "services": {
    "omniroot": "inactive",
    "opencode": "connected",
    "opencore": "inactive"
  }
}
```

### `POST /activate/{service}`

The browser sends a request only for a known service identifier. The companion should validate the identifier, authenticate/authorize the request locally, and then start or open the corresponding service.

Supported identifiers in the frontend:

- `omniroot`
- `opencode`
- `opencore`

## Security requirements

1. Bind to `127.0.0.1`, not `0.0.0.0`.
2. Use an authentication mechanism such as a locally provisioned token or origin-bound capability.
3. Allow-list service identifiers; never execute a path or shell command supplied by the browser.
4. Do not expose arbitrary command execution.
5. Rate-limit activation requests.
6. Return only non-sensitive service state.
7. If the bridge is unavailable, the website must remain a read-only public registry.

This contract is deliberately implementation-neutral. The actual OmniRoot/OpenCode/OpenCore process names, ports, and launch commands must be supplied by the local installation rather than guessed by the public website.
