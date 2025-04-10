Echo
## Go General Guidelines

### Basic Principles

- Use English for all code and documentation.
- Always specify the type of each variable and function (parameters and return value).
- Avoid using `interface{}` unless absolutely necessary.
- Define appropriate structs and interfaces.
- Use GoDoc comments for public functions, methods, and types.
- Maintain consistent spacing and formatting using `gofmt`.
- One export per file where possible.

### Nomenclature

- Use PascalCase for exported functions, types, and structs.
- Use camelCase for variables, functions, and methods.
- Use kebab-case for file and directory names.
- Use UPPERCASE for environment variables.
- Avoid magic numbers; define constants using `const`.
- Prefix boolean variables with verbs: `is`, `has`, `can`, etc.
- Use full words instead of abbreviations, except for standard ones like `API`, `URL`, etc.
- Common abbreviations:
- `ctx` for context
- `req`, `res` for request and response
- `err` for errors

### Functions

- Keep functions short and focused (preferably < 20 lines).
- Name functions with a verb and an object.
- Boolean-returning functions: `IsX`, `HasX`, `CanX`, etc.
- Procedures: `ExecuteX`, `SaveX`, `ProcessX`, etc.
- Reduce nested blocks by using early returns and helper functions.
- Prefer higher-order functions (`map`, `filter`) over loops when applicable.
- Use default values instead of checking for nil.
- Reduce parameter count using structs for inputs and outputs.
- Maintain a single level of abstraction per function.

### Data

- Avoid excessive use of primitive types; encapsulate data in structs.
- Use immutability where possible.
- Use `const` for unchanging literals.
- Use pointers where mutability is required.
- Avoid validating data in functions; use dedicated validator functions or middleware.

### Structs and Interfaces

- Follow SOLID principles.
- Favor composition over inheritance.
- Use interfaces to define contracts, but avoid unnecessary abstraction.
- Keep structs small and focused:
- Fewer than 10 fields where possible.
- Limit the number of exported methods.
- Use method receivers (`func (s *Struct) Method()`) when mutation is required.

### Error Handling

- Use Go’s error handling idioms (`if err != nil`)
- Return errors instead of panicking unless it's truly exceptional.
- Use custom error types when additional context is needed.
- Log errors appropriately and avoid excessive verbosity.

### Testing

- Use `testing` package for unit tests.
- Follow the Arrange-Act-Assert pattern.
- Use table-driven tests where applicable.
- Name test variables descriptively (`inputX`, `mockX`, `actualX`, `expectedX`).
- Write unit tests for each exported function.
- Mock dependencies using interfaces where necessary.
- Write integration tests for HTTP handlers and services.
- Use `httptest` package for API testing.

## Specific to Echo Framework

### Basic Principles

- Use a modular architecture.
- Encapsulate the API in modules:
- One package per domain.
- Handlers for HTTP endpoints.
- DTOs for request validation.
- Services for business logic.
- Repositories for data persistence.
- Use Echo’s built-in middleware for logging, recovery, and security.
- Use dependency injection for services and repositories.
- Implement request validation using `echo.Bind` and `validator` package.

### API Structure

- Define routes in a centralized location.
- Use middleware for authentication, logging, and error handling.
- Return structured JSON responses with proper status codes.
- Use service layer to handle business logic.
- Implement repository layer for database interactions.
- Use Go context (`context.Context`) for request lifecycle management.

### Error Handling

- Use Echo’s error handlers for centralized error responses.
- Return structured JSON errors with meaningful messages.
- Log errors appropriately to track issues.

### Testing

- Use `httptest` for handler testing.
- Write tests for each route, service, and repository.
- Use mocks for database and external dependencies.
- Perform end-to-end tests for major API flows.
- Ensure proper handling of request validation and error scenarios.
