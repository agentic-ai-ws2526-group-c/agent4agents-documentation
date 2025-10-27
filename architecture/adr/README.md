# Architecture Decision Records (ADRs)

## What are ADRs?

Architecture Decision Records (ADRs) are documents that capture important architectural decisions made along with their context and consequences. They help teams:

- **Maintain consistency**: All decisions are documented in the same format
- **Facilitate onboarding**: New team members can understand the "why" behind system design choices
- **Preserve knowledge**: The context and reasoning for decisions are preserved even when team members leave
- **Enable review**: Past decisions can be easily compared and reviewed

## How to Use the Template

1. **Copy the template**: Create a new file based on `template.md`
2. **Name the file**: Use the naming convention `NNNN-short-title.md` where:
   - `NNNN` is a four-digit number (e.g., 0001, 0002, etc.)
   - `short-title` is a brief, hyphenated description (e.g., `use-react-for-frontend`)
3. **Fill out the sections**:
   - Replace `ADR-NNNN` with your ADR number
   - Add the current date
   - Set the initial status to "Proposed"
   - Complete all sections with relevant information
4. **Submit for review**: Follow your team's review process before marking the ADR as "Accepted"

## Example

For a decision about choosing a database, you might create a file named `0001-use-postgresql-for-data-storage.md`.

## ADR Lifecycle

- **Proposed**: The decision is under discussion
- **Accepted**: The decision has been approved and should be implemented
- **Deprecated**: The decision is no longer relevant but kept for historical context
- **Superseded by [ADR-XXXX]**: This decision has been replaced by another ADR
