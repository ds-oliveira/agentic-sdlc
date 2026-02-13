- Modify the .md files inside .spec folder in the project root according to the user request.

**IMPORTANT: This command ONLY modifies existing files. Do NOT create files that don't exist yet.**
- requirements.md MUST exist - if it doesn't, inform the user and stop
- design.md and plan.md are optional - only modify them if they exist
- Do NOT create design.md or plan.md if they don't exist yet

# File generation flow
- requirements.md is used for generating design.md
- design.md is used for generating plan.md

# Guidelines

**Pre-Validation:**
- requirements.md MUST exist - if it doesn't, inform the user and stop
- Check if design.md exists - only modify it if it exists, do NOT create it
- Check if plan.md exists - only modify it if it exists, do NOT create it
- Do NOT create any files that don't exist - only modify existing ones

**Change Logic:**
- If the user is asking for adding/changing/removing a requirement adjust it in requirements.md and update the dependent *.md files (only if they exist: design.md → plan.md)

- If the user is asking for adding/changing/removing a design detail, validate that it won't conflict with the requirements.
    - If design.md doesn't exist, inform the user it needs to be generated first
    - If the asked changes conflict with requirements, explain why they conflict and let the user decide if it wants to proceed.
        - If the user decides to proceed, update the requirements accordingly and then update design.md and plan.md (only if plan.md exists)
    - If the asked changes don't conflict, update requirements.md if needed, then update design.md and plan.md (only if plan.md exists)

- If the user is asking for adding/changing/removing a implementation plan detail, validate that it won't conflict with the requirements and design.
    - If plan.md doesn't exist, inform the user it needs to be generated first
    - If the asked changes conflict with requirements or design, explain why they conflict and let the user decide if it wants to proceed.
        - If the user decides to proceed, update the requirements and design accordingly and then update plan.md
    - If the asked changes don't conflict, update requirements.md and design.md if needed, then update plan.md

- If plan.md exists and has phases already implemented, check the phases and make the needed changes in the code in case it's needed.


# Change
$ARGUMENTS