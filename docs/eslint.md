# Setting up ESLinter

1. Add ESLinter libraries

```bash
    npm i -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-plugin-react
```

- `eslint`: The core ESLint linting library
- `@typescript-eslint/parser`: The parser that will allow ESLint to lint TypeScript code
- `@typescript-eslint/eslint-plugin`: A plugin that contains a bunch of ESLint rules that are TypeScript specific
- `eslint-plugin-react`: React linter with typescript

2. Add `.eslintrc.js` Configuration

```json
module.exports = {
  parser: "@typescript-eslint/parser", // Specifies the ESLint parser
  parserOptions: {
    ecmaVersion: 2020, // Allows for the parsing of modern ECMAScript features
    sourceType: "module", // Allows for the use of imports
    ecmaFeatures: {
      jsx: true // Allows for the parsing of JSX
    }
  },
  settings: {
    react: {
      version: "detect" // Tells eslint-plugin-react to automatically detect the version of React to use
    }
  },
  extends: [
    "plugin:react/recommended", // Uses the recommended rules from @eslint-plugin-react
    "plugin:@typescript-eslint/recommended" // Uses the recommended rules from @typescript-eslint/eslint-plugin
  ],
  rules: {
    // Place to specify ESLint rules. Can be used to overwrite rules specified from the extended configs
    // e.g. "@typescript-eslint/explicit-function-return-type": "off",
  },
};

```

3. Add Lint command to package.json

```json
{
  "scripts": {
    "lint": "eslint '*/**/*.{js,ts,tsx}' --quiet --fix"
  }
}
```

4. Adding Prettier

```bash
   npm i -D prettier eslint-config-prettier eslint-plugin-prettier
```

To verify that your code has type errors, the `tsc --noEmit` command can used.

```bash
    npx tsc --noEmit
```
## Reference

- https://www.robertcooper.me/using-eslint-and-prettier-in-a-typescript-project
