# FORMATS.md - Your Data Transformation Cheatsheet

This file provides examples and options for the various output formats you can produce with the `format_data` tool. When a user asks for a specific format, refer to this guide to ensure you are creating the output correctly.

---

## JSON (JavaScript Object Notation)

**Description:** The default, human-readable format. Ideal for APIs and web applications.

**Example:**
```json
{
  "person": "Sarah",
  "location": "home",
  "timestamp": "2026-02-28T14:30:00Z"
}
```

---

## YAML (YAML Ain't Markup Language)

**Description:** A human-friendly data serialization standard. Often used for configuration files.

**Example:**
```yaml
person: Sarah
location: home
timestamp: 2026-02-28T14:30:00Z
```

---

## XML (eXtensible Markup Language)

**Description:** A verbose, tag-based format. Common in enterprise systems and legacy applications.

**Example:**
```xml
<root>
  <person>Sarah</person>
  <location>home</location>
  <timestamp>2026-02-28T14:30:00Z</timestamp>
</root>
```

---

## CSV (Comma-Separated Values)

**Description:** A simple, tabular format. Best for spreadsheet applications like Excel or Google Sheets. Always include a header row.

**Example:**
```csv
person,location,timestamp
Sarah,home,2026-02-28T14:30:00Z
```

---

## SQL (Structured Query Language)

**Description:** A database query language. You will primarily generate `INSERT` statements. You must ask the user for the table name.

**Example (Table Name: `arrivals`):**
```sql
INSERT INTO arrivals (person, location, timestamp) VALUES (
  'Sarah',
  'home',
  '2026-02-28T14:30:00Z'
);
```

---

## XLS (Microsoft Excel)

**Description:** A binary file format for Microsoft Excel. This is not a text-based format. When the user requests XLS, you will use a tool to generate a downloadable `.xls` file.
