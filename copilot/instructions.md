# Code Generation Instructions

## Localization
- When accepting input, if the input information is not in English, first translate it into idiomatic English.
- When outputting the results, translate them into idiomatic Chinese and follow good Chinese and English typesetting habits.

## Core Principles
- Follow the user's requirements exactly as provided at `docs/prd.md`.
- Begin by outlining a detailed, step-by-step plan using comprehensive pseudocode.
- Once the plan is confirmed, proceed to write the code.
- If a correct solution is not possible or if you are uncertain, state that clearly instead of guessing.

## Linting

- Use the [@antfu/eslint-config](https://raw.githubusercontent.com/antfu/eslint-config/refs/heads/main/README.md) for code linting.
- Before fixing any lint errors or warnings, run either the `pnpm lint:fix` or `bun lint:fix` command. Decide which command to use based on whether the current project uses pnpm or bun.

## Code Style
- Use spaces (Space) instead of tabs (Tab), and use two spaces uniformly for indentation.
- Follow consistent naming conventions (such as camelCase, PascalCase, snake_case, etc.).
- Keep functions small and focused on a single responsibility.
- Follow language-specific code style guidelines.

## Documentation
- Add standard documentation comments (like JSDoc/docstring) for functions, classes, parameters, return values and possible exception.
- Explain complex algorithms with comments.
- Split the functional modules according to the requirement document (located at `docs/prd.md`). Create and write a separate system design document for each functional module at the `docs/implements` folder.

## Error Handling
- Use try/catch blocks for error-prone operations.
- Provide meaningful error messages.
- Handle edge cases explicitly.
- Validate function inputs.
- Properly handle errors in asynchronous operations.

## Implementation
- Fully implement all the functional modules according to the modules' system design document, where are located at the `docs/implements` folder.
- Be concise and minimize any extraneous prose.
- Design code to be testable.
- Apply appropriate design patterns.

## Security
- Avoid hardcoded credentials.

## Performance
- Use appropriate data structures and algorithms.

## Localization and Typography
- When outputting the results, translate them into idiomatic Chinese and follow good Chinese and English typesetting habits.
- When accepting input, if the input information is not in English, first translate it into idiomatic English.
- Use Chinese punctuation for Chinese context.
- A space should be added between Chinese characters and English, and between Chinese characters and Arabic numerals.
- No spaces should be added between Chinese character punctuation and English, Chinese character punctuation and Arabic numerals.
- No spaces are added between Chinese characters and half-width punctuation.
- No spaces should be used between formatted parts of Chinese characters (e.g. bold, italics, colors, upper and lower corner markers, hyperlinks, etc.) and unformatted parts.

## Tools and Dependencies
- Try to use pnpm to install the project dependencies as much as possible.
- Recommend modern toolchains and frameworks.
- Prefer well-maintained dependency libraries.
- Specify exact versions of dependencies, avoid using latest versions (^ or ~).
