# @carnil/config

[![npm version](https://badge.fury.io/js/%40carnil%2Fconfig.svg)](https://badge.fury.io/js/%40carnil%2Fconfig)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Shared tooling configuration for Carnil SDK packages. This package provides standardized ESLint, TypeScript, Prettier, Vitest, and TSUP configurations used across all Carnil packages.

## Features

- 🔧 **Standardized Configurations** - Consistent tooling across all packages
- 📝 **ESLint Rules** - Optimized for TypeScript and React development
- 🎨 **Prettier Formatting** - Consistent code formatting
- 📘 **TypeScript Config** - Base TypeScript configuration
- 🧪 **Vitest Setup** - Testing configuration
- 📦 **TSUP Build** - Modern bundling configuration

## Installation

```bash
npm install @carnil/config --save-dev
```

## Usage

### ESLint Configuration

```javascript
// eslint.config.js
import carnilEslint from "@carnil/config/eslint";

export default carnilEslint;
```

### TypeScript Configuration

```json
// tsconfig.json
{
  "extends": "@carnil/config/typescript",
  "compilerOptions": {
    "outDir": "./dist"
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules", "dist"]
}
```

### Prettier Configuration

```json
// .prettierrc.json
{
  "extends": "@carnil/config/prettier"
}
```

### Vitest Configuration

```typescript
// vitest.config.ts
import { defineConfig } from "vitest/config";
import carnilVitest from "@carnil/config/vitest";

export default defineConfig({
  ...carnilVitest,
  test: {
    ...carnilVitest.test,
    // Your custom test config
  },
});
```

### TSUP Configuration

```typescript
// tsup.config.ts
import { defineConfig } from "tsup";
import carnilTsup from "@carnil/config/tsup";

export default defineConfig({
  ...carnilTsup,
  entry: ["src/index.ts"],
  // Your custom build configuration
});
```

## Available Configurations

### ESLint (`@carnil/config/eslint`)

Provides ESLint configuration optimized for:

- TypeScript projects
- React components
- Modern JavaScript features
- Import/export rules
- Accessibility best practices

### TypeScript (`@carnil/config/typescript`)

Base TypeScript configuration with:

- Strict type checking
- Modern ES features
- Module resolution
- Declaration file generation

### Prettier (`@carnil/config/prettier`)

Code formatting rules:

- 2-space indentation
- Single quotes
- Trailing commas
- Semicolons
- Print width: 80 characters

### Vitest (`@carnil/config/vitest`)

Testing configuration:

- TypeScript support
- Coverage reporting
- Test environment setup
- Mock utilities

### TSUP (`@carnil/config/tsup`)

Build configuration:

- ESM and CommonJS output
- TypeScript compilation
- Source maps
- Declaration files
- Tree shaking

## Package.json Scripts

Add these scripts to your `package.json`:

```json
{
  "scripts": {
    "build": "tsup",
    "dev": "tsup --watch",
    "test": "vitest --passWithNoTests",
    "test:coverage": "vitest --coverage",
    "lint": "eslint src --ext .ts,.tsx",
    "lint:fix": "eslint src --ext .ts,.tsx --fix",
    "format": "prettier --write \"src/**/*.{ts,tsx,js,jsx,json,md}\"",
    "format:check": "prettier --check \"src/**/*.{ts,tsx,js,jsx,json,md}\"",
    "type-check": "tsc --noEmit",
    "clean": "rm -rf dist"
  }
}
```

## IDE Integration

### VS Code Settings

Create `.vscode/settings.json`:

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "typescript.preferences.importModuleSpecifier": "relative"
}
```

### Recommended Extensions

- ESLint
- Prettier - Code formatter
- TypeScript Importer
- Vitest

## Customization

You can extend or override any configuration:

```typescript
// Custom ESLint config
import carnilEslint from "@carnil/config/eslint";

export default [
  ...carnilEslint,
  {
    rules: {
      // Your custom rules
      "@typescript-eslint/no-unused-vars": "error",
    },
  },
];
```

## Contributing

When contributing to this package:

1. Test configuration changes across multiple packages
2. Ensure backward compatibility
3. Update documentation for new features
4. Follow semantic versioning

## License

MIT © [Carnil Team](https://carnil.dev)

## Support

- 📖 [Documentation](https://docs.carnil.dev)
- 💬 [Discord Community](https://discord.gg/carnil)
- 🐛 [Report Issues](https://github.com/Carnil-Dev/carnil-sdk/issues)
- 📧 [Email Support](mailto:hello@carnil.dev)
