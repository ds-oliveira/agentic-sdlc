# Software Development Lifecycle (SDLC)

This document outlines the structured Software Development Lifecycle process used in our development workflow. The SDLC is designed to ensure comprehensive planning, design, and implementation of features with continuous feedback loops.

## SDLC Phases

### Phase 1: Initialization (Optional)

#### spec-clean

**Purpose**: Clean up any existing specification files to start fresh.

**When to use**:

* Starting a completely new feature
* Resetting after abandoned work
* Clearing outdated specifications

**Output**: Removes `.spec` directory and all related files.

---

#### spec-steering

**Purpose**: Analyze the codebase to generate comprehensive documentation for context.

**When to use**:

* Working with an unfamiliar codebase
* Need to understand the current architecture before planning
* Want AI to have better context about the project structure

**Output**: Generates three documentation files:

* Architecture overview
* Component relationships
* Technical patterns and conventions

---

### Phase 2: Requirements Definition

#### spec-requirement

Example:

```
/spec-requirements

Add a new filter option to the processBatchOrderEvents endpoint
- the new filter will be the buyer_uuid, so we can get only the events related to this uuid
- the buyer_uuid must be mapped to buyer_id while running the query at received_order_events
- do not forget to update the open ai docs by running ./gradlew openApiGenerate
```

**Purpose**: Create a formal requirements document that defines what needs to be built.

**When to use**:

* Starting any new feature or significant change
* After stakeholder discussions
* When you have a clear business need to document

**Process**:

1. Gather business requirements
2. Define user stories and acceptance criteria
3. Document constraints and dependencies
4. Create structured requirements document

**Output**: Requirements document (`.spec/requirements.md`)

**Iteration**: After this phase, you can use `spec-change` to refine requirements based on feedback.

---

### Phase 3: Design

#### spec-design

**Purpose**: Transform requirements into a comprehensive design document that serves as implementation blueprint.

**When to use**:

* After requirements are approved
* Before any code implementation
* When you need to plan the technical approach

**Process**:

1. Analyze requirements document
2. Design system architecture
3. Define component interfaces
4. Plan data structures and flows
5. Consider technical constraints and patterns

**Output**: Design document (`.spec/design.md`)

**Iteration**: Use `spec-change` to adjust the design based on technical review or new insights.

---

### Phase 4: Implementation Planning

#### spec-plan

**Purpose**: Create a detailed, step-by-step implementation plan from the design document.

**When to use**:

* After design is approved
* Before starting implementation
* When you need a clear execution roadmap

**Process**:

1. Break down design into actionable tasks
2. Sequence implementation steps
3. Identify dependencies and risks
4. Create milestone checkpoints

**Output**: Implementation plan (`.spec/plan.md`)

**Iteration**: Use `spec-change` to refine the plan based on complexity or resource considerations.

---

### Phase 5: Implementation

#### spec-implement

**Purpose**: Execute the implementation plan and write the actual code.

**When to use**:

* After the plan is approved
* During active development
* For incremental feature delivery

**Process**:

1. Follow the implementation plan step-by-step
2. Write code according to design specifications
3. Track progress through plan checkpoints
4. Handle issues and blockers

**Iteration**:

* Run multiple times for complex features
* Each run continues from where previous run left off
* It's recommended to review the code after each iteration and commit it for atomicity.
* Use `spec-change` if requirements/design need adjustment during implementation
* Use `spec-update` if you make manual code changes outside the flow

**Output**:

* Implemented code
* Updated plan with progress tracking

---

### Phase 6: Cleanup

#### spec-clean

**Purpose**: Remove all specification files after successful implementation and merge.

**When to use**:

* After feature is complete and merged
* When specifications are no longer needed
* To keep repository clean

**Output**: Removes `.spec` directory

---

## Supporting Commands (Non-Sequential)

These commands can be used at any point and are not part of the main sequential flow:

### spec-change

#### Example:

```
 /spec-change

- even though buyer_id and buyer_uuid are different naming options, the content of buyer_id is the buyer_uuid so no extra lookup mechanism is needed
- make sure all the needed indexes already exist
```

**Purpose**: Modify specification files (requirements, design, or plan) based on feedback or new information.

**When to use**:

* After receiving feedback on requirements
* When design needs adjustment
* When plan needs refinement
* During implementation when changes are needed

**Usage**: Can be used multiple times at any stage after requirements creation.

---

### spec-update

**Purpose**: Document manual code changes made outside the spec-implement flow.

**When to use**:

* You manually edited code files
* Need to sync specifications with manual changes
* Want to prevent AI from overriding your changes

**Impact**: Updates specifications to reflect manual modifications, maintaining consistency.

---

### spec-status

**Purpose**: Display the current state of the SDLC process.

**When to use**:

* After taking a break from development
* When you need to understand what's been completed
* To see what the next step should be
* When returning to a feature after context switching

**Output**: Shows:

* Current phase
* Completed tasks
* Next recommended action
* Latest task in implementation plan

---

## Workflow Examples

### Example 1: Simple Feature

```
spec-requirement → spec-design → spec-plan → spec-implement → spec-clean
```

### Example 2: Complex Feature with Iterations

```
spec-requirement → spec-change → spec-change →
spec-design → spec-change →
spec-plan →
spec-implement → spec-implement → spec-implement →
spec-clean
```

### Example 3: Feature with Manual Changes

```
spec-requirement → spec-design → spec-plan →
spec-implement → [manual code changes] → spec-update →
spec-implement → spec-clean
```

### Example 4: Unfamiliar Codebase

```
spec-steering →
spec-requirement → spec-design → spec-plan → spec-implement → spec-clean
```

### Example 5: Starting Fresh

```
spec-clean → spec-requirement → spec-design → spec-plan →
spec-implement → spec-clean
```

---

## Best Practices

### 1. Always Start with Requirements

Never skip the requirements phase. Clear requirements prevent scope creep and ensure alignment.

### 2. Use spec-change Liberally

Don't hesitate to refine specifications. It's better to iterate on documents than fix code later.

### 3. Leverage spec-status

Use `spec-status` frequently, especially after breaks or when returning to a feature. It helps maintain context.

### 4. Document Manual Changes

Always run `spec-update` after manual code modifications to keep specifications synchronized.

### 5. Clean Up Afterwards

Run `spec-clean` after merging to keep the repository clean and avoid confusion with old specifications.

### 6. Use spec-steering for Context

When working with a new or complex codebase, use `spec-steering` to give the AI better context for all subsequent phases.

### 7. Iterate During Implementation

Don't try to implement everything in one pass. Use multiple `spec-implement` runs for complex features, allowing for incremental progress and validation.

### 8. Embrace the Feedback Loop

The optional `spec-change` after each phase exists for a reason. Use it to incorporate feedback and refinements.

---

## Benefits of This SDLC

1. **Structured Approach**: Clear phases prevent chaotic development
2. **Documentation**: Every feature has comprehensive documentation
3. **Iteration Support**: Built-in feedback loops at every stage
4. **Flexibility**: Optional phases for different scenarios
5. **Context Preservation**: spec-status helps maintain context across sessions
6. **AI-Friendly**: Provides AI with clear, structured context for better assistance
7. **Incremental Delivery**: Support for iterative implementation
8. **Change Management**: Explicit handling of requirement changes and manual modifications

---

## Conclusion

This SDLC provides a comprehensive framework for feature development that balances structure with flexibility. By following this process, teams can ensure thorough planning, clear documentation, and successful implementation while maintaining the ability to adapt to changing requirements and feedback. The key to success is understanding when to use each command and embracing the iterative nature of the process.
