# tsconfig

> Shared [TypeScript config](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) for my projects

## Install

```sh
npm install --save-dev @rubiin/tsconfig
```

_This config requires TypeScript 6 or later. Though it may work for Typescript 5_

## Usage

### Preset Types

| Preset  | Extends                                          | Type environment                                      |
| ------- | ------------------------------------------------ | ----------------------------------------------------- |
| Base    | `@rubiin/tsconfig`                               | No explicit `types`; strict runtime-agnostic defaults |
| Node    | `@rubiin/tsconfig/configs/tsconfig.node.json`    | `types: ["node"]`                                     |
| Nest    | `@rubiin/tsconfig/configs/tsconfig.nest.json`    | `types: ["node", "express", "jest"]`                  |
| Web     | `@rubiin/tsconfig/configs/tsconfig.web.json`     | DOM libs via `lib: ["ESNext", "DOM", "DOM.Iterable"]` |
| Bundler | `@rubiin/tsconfig/configs/tsconfig.bundler.json` | No explicit `types`; bundler module resolution        |

Base preset (runtime-agnostic)

```json
{
  "extends": "@rubiin/tsconfig",
  "compilerOptions": {
    "outDir": "dist"
  }
}
```

Node preset (ESM-first)

```json
{
  "extends": "@rubiin/tsconfig/configs/tsconfig.node.json",
  "compilerOptions": {
    "outDir": "dist"
  }
}
```

Nest preset (Node + decorators)

```json
{
  "extends": "@rubiin/tsconfig/configs/tsconfig.nest.json"
}
```

Web preset (bundler-first)

```json
{
  "extends": "@rubiin/tsconfig/configs/tsconfig.web.json"
}
```

Bundler preset (bundler-first)

```json
{
  "extends": "@rubiin/tsconfig/configs/tsconfig.bundler.json"
}
```

When you are targeting a higher version of Node.js, check the relevant ECMAScript version and add it as `target`:

```json
{
  "extends": "@rubiin/tsconfig",
  "compilerOptions": {
    "outDir": "dist",
    "target": "ES2023"
  }
}
```
