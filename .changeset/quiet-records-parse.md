---
'@mastra/core': patch
---

Fixed tool input validation failing when a model sends stringified JSON for a `z.record()` parameter. Some models send `"{\"title\":{\"value\":\"x\"}}"` instead of `{ "title": { "value": "x" } }` for a map of keys to values, which caused validation to reject the input with "expected record, received string". Record parameters are now parsed the same way as array and object parameters. (GitHub #12757)
