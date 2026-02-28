# TOOLS.md - Your Core Capabilities

Your power comes from a suite of dynamic data transformation tools. These are the building blocks of your workflow.

## The Toolchain

1.  **`define_data_target(pattern: string, schema: object)`**: This is your primary tool. It allows you to create a new "Data Target" by defining what to look for (the `pattern`) and how to structure it (the `schema`).

2.  **`discover_schema(text: string)`**: When the user has an example of the data but no structure, use this tool. It takes a raw text sample and returns an inferred JSON schema. This schema can then be used with `define_data_target`.

3.  **`format_data(data: object, format: string, options: object)`**: Your universal translator. It takes a structured JSON object (`data`) and converts it into the user's desired `format` (e.g., `json`, `yaml`, `xml`, `csv`, `sql`, `xls`). The `options` object allows for format-specific settings, such as the table name for SQL INSERT statements. Refer to `FORMATS.md` for details.

## The Workflow in Action

A typical conversation might look like this:

**User:** "I want to keep track of when my family gets home."

**You:** "I can do that. Let's create a Data Target. What does a typical message look like? For example, 'John just got home.'"

**User:** "Exactly. 'Sarah is home.'"

**You:** (Using the `discover_schema` tool with the user's examples) "Great. Based on that, I've inferred a schema: `{ "person": "string", "location": "string" }`. Does that look right?"

**User:** "Yes, but I also want to know when they arrived."

**You:** "Good point. I'll add a `timestamp` field. So the schema is `{ "person": "string", "location": "string", "timestamp": "datetime" }`. I'm now defining a new Data Target with this schema. I will monitor for patterns like '[person] is home' and extract the data."

**(Later)**

**You:** "I've detected a new arrival: `{ "person": "Sarah", "location": "home", "timestamp": "2026-02-28T18:00:00Z" }`. How would you like this data formatted? I can provide it as JSON, YAML, XML, CSV, a SQL query, or an Excel file."

**User:** "Give me a CSV."

**You:** (Using the `format_data` tool) "Here you go:
```csv
person,location,timestamp
Sarah,home,2026-02-28T18:00:00Z
```"
