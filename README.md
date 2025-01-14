# Cursor Boilerplate Rules

Always use "bun" as package manager
Always speak to me in Turkish and if you are going to write a comment line or define a variable in the codebase always write in English.
All shadcn/ui components are installed in the project, you do not need to install an additional shadcn/ui component.

This boilerplate serves as the foundation for your projects. Below are the predefined packages, configurations, and rules for working with this setup. Follow these guidelines strictly to ensure compatibility and maintainability.

## Immutable Boilerplate Base

- The predefined setup in this boilerplate (e.g., `package.json`, `vite.config.ts`, `tsconfig.json`) must remain unchanged.
- You are allowed to extend the boilerplate by adding new features or configurations, but existing ones should not be removed or modified.
- Exceptions are made for adjustments to settings specific to your project requirements, but these must align with the boilerplate's core principles.

## Standard Compliance

- This project strictly adheres to modern web development standards.
- **Type Definitions**: TypeScript is mandatory for this project. Ensure all code is strongly typed.
- **ESLint**: Use the provided ESLint configuration to maintain consistent coding standards. Avoid disabling rules unless absolutely necessary.
- **Prettier**: Use the predefined Prettier configuration for code formatting.
- Ensure that all additional code and configurations align with these standards.

## Default Libraries and Tools

The boilerplate includes the following packages and tools by default:

### Core Libraries

- **React**: Latest stable version for building user interfaces.
- **Vite**: A fast build tool preconfigured for React and TypeScript.
- **TypeScript + SWC**: For type safety and high-speed compilation.

### State Management

- **Zustand**: A minimalistic state management library designed for simplicity and flexibility. **Do not use Redux or Redux Toolkit** for state management. Zustand is the only state management solution supported by this boilerplate.

### UI Components

- **shadcn/ui**: A complete set of customizable UI components for building modern interfaces.

### Styling

- **TailwindCSS**: The primary styling tool for the project.
  - Avoid using external styles unless absolutely necessary.
  - Do not modify `index.css` or TailwindCSS configuration files unless explicitly permitted.
  - If changes are required, include the following:
    - A detailed explanation of the purpose of the changes.
    - Specific examples of what you need to add or modify.
    - Obtain approval before making the changes.

### Folder Structure

To maintain consistency and organization, adhere to the following folder structure:

- `src/components`
  - `src/components/ui`: Contains **shadcn/ui** components for building consistent and reusable UI elements.
  - `src/components/common`: Shared components like buttons, modals, and headers that are not tied to `shadcn/ui`.
  - `src/components/features`: Feature-specific components for individual application modules.
- `src/state`: Contains Zustand global state management files.
- `src/services`: For HTTP services and API integrations.
  - **Usage**: All HTTP requests should use an Axios instance configured with a `baseURL` set in `.env`.
    - Example:
      ```typescript
      import axios from 'axios';

      const api = axios.create({
        baseURL: process.env.VITE_API_BASE_URL,
      });

      export default api;
      ```
- `src/styles`: For additional custom styles if necessary (use sparingly and align with TailwindCSS).
- `src/utils`: Helper functions or utility files.
- `src/pages`: Page components that define the application's main views.
- `src/hooks`: Custom hooks for managing reusable logic.
- `public/`: Static assets like images and fonts.

### Aliases

- Use `@/` as an alias for the `src` directory to simplify imports.
  - Example: `import Button from '@/components/ui/Button';`

### Do Not Replace or Remove

- These libraries form the foundation of the boilerplate. Do not replace or remove them.
- You may add complementary libraries or tools, but they must integrate seamlessly with the existing setup.

## Usage of Additional Packages

For additional functionality like animations, storage, or data fetching, you must use standardized and well-documented packages. Below is a list of commonly used libraries and their purposes:

### Local Storage

- **Purpose**: Manage and persist data in the browser's `localStorage`.
- **Recommended Package**: [`store2`](https://github.com/nbubna/store) for a simple and extensible interface.
  - **Implementation**: Store reusable logic for `localStorage` in the `src/utils` folder.

### Animations

- **Purpose**: Add animations and transitions to your project.
- **Recommended Package**: [`framer-motion`](https://www.framer.com/motion/) for declarative and powerful animations.

### HTTP Requests

- **Purpose**: Fetch data from APIs.
- **Recommended Package**: [`axios`](https://axios-http.com/) for a robust and feature-rich HTTP client.
  - **Best Practices**: Always use a central Axios instance.
  - **Folder Location**: Place all service files in `src/services`.

### Form Validation

- **Purpose**: Validate user inputs in forms.
- **Recommended Package**: [`react-hook-form`](https://react-hook-form.com/) for minimal and flexible form handling.

### Date and Time Handling

- **Purpose**: Manage and manipulate dates and times.
- **Recommended Package**: [`date-fns`](https://date-fns.org/) for lightweight and modular date utilities.

### Utility Libraries

- **Purpose**: Provide additional utility functions.
- **Recommended Package**: [`lodash`](https://lodash.com/) for a comprehensive utility library.

### GraphQL

- **Purpose**: Query and manipulate data via GraphQL APIs.
- **Recommended Package**: [`@apollo/client`](https://www.apollographql.com/docs/react/) for an advanced GraphQL client.

For any of these needs, provide a brief explanation of why the library is necessary and how it integrates with the current setup. Ensure it follows the project's coding standards.

### Restricted Usage

- Do not use additional libraries unless absolutely necessary and approved.
- Provide a clear rationale and usage documentation for any new library added to the project.

## Documentation for Extensions

When adding new libraries, tools, or configurations:

- Include concise documentation explaining:
  - The purpose of the addition.
  - How it is used in the project.
  - Any potential issues and their resolutions.
- Documentation should be added to a dedicated section within the project or a separate markdown file.

## Development Workflow

- Build your projects on top of this boilerplate without altering the foundational setup.
- Ensure any additional features enhance the existing structure without conflicting with the default configurations.
- Follow best practices for clean and maintainable code.

## Recommended Practices

- Regularly update dependencies to their latest versions while ensuring compatibility.
- Test all changes thoroughly in a development environment before pushing to production.
- Maintain consistency in code style and structure by adhering to provided standards.

---

For any questions or issues related to the boilerplate, refer to the included documentation or reach out to the maintainers.
