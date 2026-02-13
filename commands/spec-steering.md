Please analyze this codebase and generate three detailed documentation files in markdown format:

## 1. `.spec/product.md` - Product Overview
Create a high-level product overview including:
- **Product Overview**: What the system does and its primary purpose
- **Key Features**: Main functional capabilities (up to 8 bullet points with brief descriptions)
- **Business Context**: Why this system exists, what problems it solves, and how it fits into the larger ecosystem

Focus on **what** the system does, not **how** it does it. Write for stakeholders, new team members, and anyone trying to understand the product's purpose.

## 2. `.spec/structure.md` - Project Structure
Document the codebase organization including:
- **Root Level Organization**: Top-level directories with brief explanations
- **Main Application Structure**: Key source code directories organized by architectural layer or concern
- **Key Architectural Patterns**: Important design patterns used (e.g., delegate pattern, repository pattern, factory pattern)
- **Database Structure**: Migration locations, key tables/collections
- **Testing Structure**: Test organization and special test utilities
- **Static Resources**: Configuration files, schemas, templates
- **Naming Conventions**: Conventions for classes, files, packages, database entities, etc.

Use code blocks and ASCII tree structures to illustrate directory hierarchies. Be specific about what lives where.

## 3. `.spec/tech.md` - Technology Stack & Commands
Provide technical reference including:
- **Core Technologies**: Language version, framework, runtime, build tool, database, caching, message queues, auth mechanism, monitoring tools
- **Key Dependencies**: Important libraries and SDKs organized by category
- **Common Commands**: Practical commands developers use daily:
  - Development setup (language/runtime installation)
  - Build & test commands
  - Local development commands
  - Linting/formatting
  - Code generation (if applicable)
- **Code Generation**: Any auto-generated code and how to regenerate it
- **Environment Setup**: Steps to configure local environment

Include actual command examples that developers can copy-paste.

---

**Requirements:**
- Generate all three files in markdown format
- Keep each file focused on its specific concern (don't repeat information across files)
- Use clear headers and bullet points for scanability
- Include specific examples from the actual codebase
- Be concise but comprehensive - each file should be up to 400 lines
- If certain sections don't apply to this project, note that briefly rather than inventing content

**Output Format:**
Create each file as a separate artifact so I can save them individually.
