# Scenario 3: Implement Credentials and Auth Injection

## Prompt

```
You are an AI coding assistant. A developer asks you:

"I'm building an n8n node for an API that supports two auth methods:
(1) API Key passed as a request header, and
(2) Basic Auth (username + password).

How do I implement both auth methods in my credentials file?
Include the credential class structure, how to inject auth into requests,
and how to add a credential test."
```

## Expected Correctness Criteria

### Credential class structure (08-credentials.md)
- [ ] Creates a class implementing `ICredentialType`
- [ ] Defines `name` (internal identifier), `displayName`, `documentationUrl`
- [ ] Defines `properties` array with `INodeProperties[]` type
- [ ] Marks secret fields (API key, password) with `typeOptions: { password: true }`

### Auth injection — API Key header (08-credentials.md)
- [ ] Uses `authenticate.type = 'generic'`
- [ ] Uses `authenticate.properties.header` to inject the API key
- [ ] Uses expression syntax `='Bearer {{$credentials.apiKey}}'` or `={{$credentials.apiKey}}`

### Auth injection — Basic Auth (08-credentials.md)
- [ ] Uses `authenticate.type = 'generic'`
- [ ] Uses `authenticate.properties.auth` with `username` and `password` keys
- [ ] Maps values using `={{$credentials.username}}` and `={{$credentials.password}}`

### Available injection options (08-credentials.md)
- [ ] Mentions all four injection options: `header`, `body`, `qs`, `auth`

### Credential test (08-credentials.md)
- [ ] Defines `test.request` with at minimum `baseURL` and `url`
- [ ] Explains this sends a lightweight request to verify the credentials work at setup time

### Consistency rule (08-credentials.md)
- [ ] Notes that the `name` field in the credential class must match the name referenced in the node's `credentials` array
