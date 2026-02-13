- IF there is a .spec/plan.md file in the project root: inform what is the latest task implement and what's the next one.
Expected output format:
```
Based on the implementation plan, here's the current status:

  Latest Completed Task: Task 3.2 - Configuration Validation

  Next Task: Task 4 - Structured Logging System

  ---
  Summary:
  - ✅ Completed: Project setup, core interfaces, data models, and configuration management (Tasks 1-3)
  - 🔄 Next up: Implementing the structured logging system using zap or logrus with correlation ID support, configurable log levels, and request/response logging

  The project is in the implementation phase with approximately 25% of tasks completed. The foundation (project structure, interfaces, models, and configuration) is in place, and the next step is to implement
  the logging infrastructure before moving on to the cache and weather provider implementations.
```
- ELSE if there is a .spec/design.md file in the project root: inform that the spec is on desing phase.
- ELSE if there is a .spec/requirements.md file in the project root: inform that the spec is on requirements phase.
- ELSE inform there is no specification workflow active at the moment.


