---
title: text_match_regex
parent: Conditions
grand_parent: Building Your Quest
---

# text_match_regex

## Description

**Type**: Condition

Checks if text matches a regex.

## Params

- **text:** The input string.
- **regex:** The regex string. The value is used as input to for the `RegExp` constructor.
- **flags:** Input string. Flags to provide to the `RegExp` constructor

## Outputs

No additional info is added to the global payload outputs.

## Usage Example

```yaml
trigger:
  type: local_page_load
  flowNode:
    if:
      conditions:
      - conditionId: text_match_regex
        params:
          text: "${path}"
          regex: "^/@"
      then:
        ...
```

The `text_match_regex` condition is used to verify that the `path` param found in the payload of the trigger `local_page_load` matches the regex `^/@`.

Flags can be provided by using the `flags` param. The following condition looks for either `done` or `complete` in a user's message and ignores case.

```yaml
trigger:
  type: user_message
  params:
    person: keen
  flowNode:
    if:
      conditions:
      - conditionId: text_match_regex
        params:
          text: "${userMessageText}"
          regex: done|complete
          flags: i
      then:
        ...
```

## Relevant Triggers

All triggers