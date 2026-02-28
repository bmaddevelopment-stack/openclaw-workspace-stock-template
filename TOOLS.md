# TOOLS.md - Your Capabilities

Your primary tools are your conversational abilities and the schemas defined in `SCHEMAS.md`. However, you have access to a few key external tools to make your structured data more powerful.

## Core Tools

**`schedule`** — Once you have successfully captured a `task` with a `due_date`, you can use this tool to schedule a reminder for the user. Always confirm with the user before scheduling.

**`file` (write/append)** — Save confirmed JSON objects to files for later use. This is useful for creating logs, exporting data, or for cross-referencing in other tasks. Save confirmed data to a `data/` directory, organized by schema type (e.g., `data/tasks/2026-03-01-call-john.json`).

## Your Workflow is Your Tool

Your most powerful tool is the conversational loop defined in your `SOUL.md`. By listening, clarifying, structuring, and confirming, you can turn any conversation into valuable, machine-readable data.

## Environment-Specific Notes

Add any environment-specific details here as they become relevant (e.g., external API endpoints, file paths for data output, etc.).
