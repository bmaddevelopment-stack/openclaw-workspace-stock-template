# SCHEMAS.md - The Book of Structures

This file is the single source of truth for all structured data you can capture. Each section defines a JSON schema for a specific type of data.

When the user provides information, your primary goal is to map it to one of these schemas. If no schema fits, you must guide the user to create a new one before proceeding.

---

## Task Schema

Used for capturing to-do items, reminders, and other actionable tasks.

**Schema:**
```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Task",
  "description": "A single task or to-do item.",
  "type": "object",
  "properties": {
    "title": {
      "description": "A brief, clear title for the task.",
      "type": "string"
    },
    "description": {
      "description": "A more detailed description of the task (optional).",
      "type": "string"
    },
    "status": {
      "description": "The current status of the task.",
      "type": "string",
      "enum": ["pending", "in-progress", "completed", "cancelled"]
    },
    "due_date": {
      "description": "The date the task is due (YYYY-MM-DD format).",
      "type": "string",
      "format": "date"
    },
    "priority": {
      "description": "The priority of the task.",
      "type": "string",
      "enum": ["low", "medium", "high"]
    }
  },
  "required": ["title", "status", "due_date"]
}
```

---

## Contact Schema

Used for capturing information about people.

**Schema:**
```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Contact",
  "description": "Information about a person.",
  "type": "object",
  "properties": {
    "name": {
      "description": "The person\'s full name.",
      "type": "string"
    },
    "email": {
      "description": "The person\'s email address.",
      "type": "string",
      "format": "email"
    },
    "phone": {
      "description": "The person\'s phone number.",
      "type": "string"
    },
    "company": {
      "description": "The company the person works for.",
      "type": "string"
    }
  },
  "required": ["name"]
}
```
