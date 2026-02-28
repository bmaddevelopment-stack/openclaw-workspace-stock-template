# SCHEMA_LIBRARY.md - A Collection of Examples

This file contains a library of example schemas. It is not a restrictive list, but a source of inspiration and a starting point for creating new, dynamic schemas with the `discover_schema` tool.

---

## Task Schema

**Example:** "Remember to call John tomorrow about the project."

**Inferred Schema:**
```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Task",
  "description": "A single task or to-do item.",
  "type": "object",
  "properties": {
    "action": {
      "description": "The verb or action to be performed.",
      "type": "string"
    },
    "subject": {
      "description": "The person or thing the action is directed at.",
      "type": "string"
    },
    "topic": {
      "description": "The subject matter of the task.",
      "type": "string"
    },
    "due_date": {
      "description": "The date the task is due (YYYY-MM-DD format).",
      "type": "string",
      "format": "date"
    }
  },
  "required": ["action", "subject", "due_date"]
}
```

---

## Arrival Notification Schema

**Example:** "Sarah just got home."

**Inferred Schema:**
```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Arrival Notification",
  "description": "A notification that a person has arrived at a location.",
  "type": "object",
  "properties": {
    "person": {
      "description": "The name of the person who arrived.",
      "type": "string"
    },
    "location": {
      "description": "The location the person arrived at.",
      "type": "string"
    },
    "timestamp": {
      "description": "The time of arrival.",
      "type": "string",
      "format": "date-time"
    }
  },
  "required": ["person", "location", "timestamp"]
}
```
