# tsconfig

> Shared [TypeScript config](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) for my projects

## Install

```sh
npm install --save-dev @rubiin/tsconfig
```

_This config requires TypeScript 5 or later._

## Usage

`tsconfig.json`

```json
{
  "extends": "@rubiin/tsconfig",
  "compilerOptions": {
    "outDir": "dist"
  }
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
