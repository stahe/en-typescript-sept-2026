# Introduction to TypeScript Through Examples

The course **Introduction to TypeScript Through Examples** is
the 2026 update of the ECMAScript 6 course originally written by Serge Tahé
in October 2019. The complete course (text, explanations, annotated output results) is published at [stahe.github.io/typescript-sept-2026](https://stahe.github.io/typescript-sept-2026).

**This course and its code were written entirely by Anthropic’s AI, Claude.**

## Prerequisites

- **[Node.js](https://nodejs.org) 26 or newer** — required for the
  `ecmascript-2026/` and `temporal/` chapters to run correctly
  (see below); the other chapters work with Node 18–22.
- **npm** (included with Node.js).

Each script runs the same way, using **[tsx](https://github.com/privatenumber/tsx)**:
no prior compilation is required; `tsx` transpiles and executes the
`.ts` file on the fly.

To simply check the types of the entire project without running anything:

```bash
npm run check
```

## Project Organization

One folder per chapter of the course:

| Folder | Chapter |
|---|---|
| `basics/` | TypeScript Basics |
| `arrays/` | Arrays |
| `objects/` | Object Literals |
| `strings/` | Strings |
| `regexp/` | Regular Expressions |
| `functions/` | Functions |
| `exceptions/` | Errors and Exceptions |
| `modules/` | Modules |
| `async/` | Event-Driven Programming and Asynchronous Functions |
| `http/` | TypeScript HTTP Functions (fetch, axios) |
| `classes/` | Classes |
| `tax-client/` | HTTP clients for the tax calculation service (3 versions: layered console, then browser with Webpack) |
| `new-features/` | ECMAScript 2020–2024 new features |
| `ecmascript-2026/` | ECMAScript 2026 features |
| `temporal/` | `Temporal`, the modern replacement for `Date` |

Each folder contains its own `README.md`, a concise summary of the corresponding educational content from the full course.

## ⚠️ Chapters Requiring Node 26

The `ecmascript-2026/` and `temporal/` folders illustrate very recent language features, not all of which are available in all versions of Node.js—some ECMAScript 2026 features themselves are not
yet implemented by all JavaScript engines despite their official adoption
by TC39 (see `ecmascript-2026/README.md` for details). The
relevant scripts use `typeof` to check the availability of each feature before using it, and display a clear message
if it’s not available, rather than crashing.

## Special Case: `client impots/client http 3`

This subfolder is a standalone **webpack** mini-project (with its own
`package.json` and `tsconfig.json`), intended to run in a
browser rather than with Node.js—see its own `README.md`.

## How the code was typed

The original course deliberately taught dynamic behaviors
specific to JavaScript (a variable that changes type, an array that mixes
multiple types, an object to which properties are added later...).
To remain faithful to these demonstrations while producing authentic TypeScript:

- **precise types** (`string`, `number`, dedicated interfaces...) wherever the data actually has a fixed form—in most cases;
- **explicit `any`**, commented out, when the script specifically demonstrates the dynamic flexibility of JavaScript—a deliberate choice, distinct from an implicit `any`
  (which `tsconfig.json` prohibits via `strict: true`);
- **`@ts-expect-error`**, with a comment, when the script intentionally demonstrates an error: TypeScript detects it at compile time, whereas JavaScript only revealed it at runtime.

## Project Configuration

- **`tsconfig.json`**: `strict` mode enabled, `NodeNext` resolution (relative imports retain the `.js` extension, which actually points to the corresponding `.ts` source file—a modern convention for Node + ESM + TypeScript). Contains `"types": ["node"]`, required since TypeScript 6.0
  so that Node globals (`console`, `process`...) remain recognized.
- **`.eslintrc.cjs`**: `@typescript-eslint` parser, to correctly analyze
  TypeScript syntax (types, interfaces, private fields
  `#x`...).

## Author

Claude AI from Anthropic [[https://claude.com/fr](https://claude.com/fr)], Serge Tahé — [stahe.github.io](https://stahe.github.io)


