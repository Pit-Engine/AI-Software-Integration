# DESY Assistant public web search

Status as of 27 November 2026 — Candidate capability. Ordinary Chat Completions requests using `coding` and `reasoning` worked in a user-run smoke test. Web search and hosted knowledge collections still need live verification against DESY.

## Request to verify

The DESY VS Code setup file `INSTALL-PROMPT.md` reports that the following options triggered server-side web search on 28 August 2026. It reports receiving a `sources` array with URLs and snippets. Open WebUI documents these options for its legacy search mode. Treat them as provider-specific options and verify the current DESY response. [Open WebUI API documentation](https://docs.openwebui.com/reference/api-endpoints/)

Send a synthetic public query to `POST https://assistant.desy.de/api/chat/completions` using the `coding` model, the usual `messages` field, and these additions:

```json
{
  "features": { "web_search": true },
  "params": { "function_calling": "legacy" }
}
```

For a smoke test, ask for the official ASTRA documentation on 3D field maps. Inspect the returned source metadata and confirm that a cited page supports the claim. Record the test date, model, response shape, and any observed capability limits.

## Integration boundary

Offer **Search public documentation** as an explicit optional action. Preview the exact public query before sending it. Keep application state, internal or unpublished material, logs, and file paths out of the search payload because DESY says search inputs may be passed to external services. Display the retrieved sources with the answer when available. [DESY IT guidance](https://it.desy.de/services/desy_assistant/index_eng.html)

Evaluate curated technical references and verified examples as a separate capability. Open WebUI documents knowledge collections. Availability and permissions for those collections on DESY remain to be confirmed. [Open WebUI API documentation](https://docs.openwebui.com/reference/api-endpoints/)
