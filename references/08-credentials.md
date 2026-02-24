# Credentials File (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/build/reference/credentials-files/
- Retrieved At (UTC): 2026-02-06T18:01:47Z
- Scope: Credential file schema, auth injection, and credential testing.

## Purpose

Credentials files define how n8n collects and injects authentication details for API calls.

## Baseline Structure

1. Import credential-related types.
2. Create credential class implementing `ICredentialType`.
3. Define:
   - `name`
   - `displayName`
   - `documentationUrl`
   - `properties`
   - `authenticate`
   - `test`

## Auth Injection Pattern

Use `authenticate.type = 'generic'` with one of:

- `header`
- `body`
- `qs`
- `auth`

Map values from credentials object expressions such as `={{$credentials.apiKey}}`.

## Credential Test

Define a lightweight verification request in `test.request` to validate credentials at setup time.

## Implementation Rules

- Match auth behavior exactly to provider requirements.
- Mark secret fields appropriately (for example password-like strings).
- Keep property naming stable and referenced consistently from node code.
