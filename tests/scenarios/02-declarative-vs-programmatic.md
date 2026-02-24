# Scenario 2: Choose Declarative vs Programmatic Style

## Prompt

```
You are an AI coding assistant. A developer is about to build several n8n nodes
and needs to decide which building style to use for each case:

1. A node that polls a REST API every minute for new records (trigger node).
2. A node that wraps a GraphQL API.
3. A node that calls a REST API to create/update/delete CRM contacts.
4. A node that fetches data and reshapes it heavily before outputting.

For each case, recommend declarative or programmatic style and explain why.
Then describe the key technical difference between the two styles.
```

## Expected Correctness Criteria

### Default rule (03-approach-selection.md)
- [ ] States that declarative is the default/preferred style for most nodes
- [ ] States declarative is best suited to REST API integrations

### Case-by-case decisions (03-approach-selection.md)
- [ ] Case 1 (trigger) → programmatic (triggers require programmatic style)
- [ ] Case 2 (GraphQL) → programmatic (non-REST APIs require programmatic style)
- [ ] Case 3 (REST CRUD) → declarative (standard REST, no triggers or custom transforms)
- [ ] Case 4 (custom transforms) → programmatic (custom data transformation requires programmatic style)

### Technical difference (03-approach-selection.md, 04-declarative.md, 05-programmatic.md)
- [ ] Declarative style uses `routing` key inside operation options to define the request
- [ ] Programmatic style requires an `execute()` method that reads inputs and builds requests
- [ ] Declarative does not need an `execute()` method

### Programmatic specifics (05-programmatic.md)
- [ ] Mentions `getInputData()` to access incoming items
- [ ] Mentions iterating over items with a `for` loop using item index
- [ ] Mentions `httpRequestWithAuthentication` for making authenticated requests
- [ ] Mentions `constructExecutionMetaData` for building output with item linking
- [ ] Mentions handling `continueOnFail()` inside the loop for per-item error handling
