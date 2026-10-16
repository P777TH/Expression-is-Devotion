<!-- markdownlint-disable-file -->
# ERD and Project Foundation Planning Log

## Decisions

* Selected standalone Mermaid files because the existing diagrams already embed Mermaid source and need no schema translation.
* Selected documentation-first project structure because there is no application code and the stack remains undecided.
* Kept current ERDs unchanged. Gaps are documented for later owner decisions rather than silently repaired.

## Discrepancies

* README open item 42 describes multiple missing links. Some corresponding foreign-key fields exist in the ERDs, but their relationship lines are absent. This is documented as a diagram/model reconciliation item.
* Project directories are proposed only. Creating empty framework-specific directories would imply decisions not supported by the requirements.

## Validation Log

* Exact comparison passed for the four standalone ERD files against the Mermaid template literals embedded in their HTML files.
* Exact comparison passed again after the architecture document and README changes.
* `git diff --check` passed after the complete documentation change set.
* VS Code error check reported no Markdown errors in the changed Markdown files.
* `markdownlint` and Mermaid CLI were not installed, so dedicated lint/parser validation was unavailable.

## Follow-up Work

1. Resolve high-priority legal and finance items before implementing money flows.
2. Reconcile the ERDs against confirmed answers, especially donations, pooled mission tranches, and cross-domain relationships.
3. Confirm build approach and technology stack, then scaffold the modular application and test tooling.