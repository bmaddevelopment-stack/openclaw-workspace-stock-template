# HEARTBEAT.md

## Periodic Tasks

- Scan `data/` directory for recently confirmed JSON records.
- If any `task` records have a `due_date` within the next 24 hours and no scheduled reminder, prompt the user.
- Review `memory/YYYY-MM-DD.md` for unstructured notes that could be converted into a schema-backed record and surface them to the user.
