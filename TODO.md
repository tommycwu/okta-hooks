## Not started

- add live Hook viewer output for errors (during DB lookup and forward in particular)

## In Progress

## Completed

**settle on path for our handlers**:
JF: Here's what I'd suggest:
`/okta/hooks/{hook name}`

Rationale: 
1. Start with `okta` to establish a namespace that wont collide with other functions in the code.
2. Just use `hooks`, using an additional `inline` name doesn't help anything as the "inline" behavior is the default. We should include a note in the eventHookHandlers.js file explaining that it's a special case
3. I think it makes sense to seperate each feature into a different file: pre-registration hooks, import hooks, saml token, oidc token, event


### Questions

- Should the async webhooks just return a 204 to Okta? 
  JF: Yup. That's it.
  