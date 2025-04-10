Replit - TypeScript, React, Express, Shadcn UI, Radix UI,Tailwind, Drizzle, Zod
You are an expert in TypeScript, React, Express, Shadcn UI, Radix UI,Tailwind, Drizzle, Zod, Vite
Code Guidelines
-Concise & Technical: Write clear, technical TypeScript code.
-Functional & Declarative: Use functional components and declarative patterns; avoid classes.
-Modular: Prefer helper functions and modular files.
-Dual Environments: Organize code into client and server folders.
Naming Conventions
-Directories: Lowercase with dashes (e.g., client/auth-wizard, server/api).
-Exports: Use named exports for components and utilities.
-Variables: Use descriptive names (e.g., isLoading, hasError).
TypeScript Usage
-Strict Typing: Use TypeScript everywhere; prefer interfaces for objects.
-Validation: Use drizzle-zod for schema validation.
-Components: Use functional components with proper TS interfaces.
Syntax and Formatting
-Pure Functions: Use function for pure functions.
-Concise Conditionals: Use minimal syntax for simple conditionals.
-Declarative JSX: Write clear, declarative JSX.
UI and Styling
-Libraries: Use Shadcn UI and Radix UI.
-Tailwind CSS: Follow a mobile-first, responsive design.
-Structure: Place UI components in client and separate them from business logic.
Server-Side Considerations
-Express: Organize routes, middleware, and controllers in server.
-Database: Use drizzle-orm with drizzle-zod for type-safe DB interactions.
-Config: Manage environment variables with dotenv and sessions with express-session.
Performance Optimization
-SSR & Splitting: Optimize loads with SSR only when needed.
-React Query: Use tanstack/react-query for client data fetching.
-Dynamic Loading: Wrap non-critical components in Suspense.
-Minimize Client Hooks: Reduce useEffect and similar hooks.
