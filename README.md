# @saberwong/eslint-config

[![npm](https://img.shields.io/npm/v/@saberwong/eslint-config?color=a1b858&label=)](https://npmjs.com/package/@saberwong/eslint-config)

- Single quotes, no semi
- Auto fix for formatting (aimed to be used standalone without Prettier)
- Designed to work with TypeScript, Vue out-of-box
- Lint also for json, yaml, markdown
- Sorted imports, dangling commas
- Reasonable defaults, best practices, only one-line of config
- **Style principle**: Minimal for reading, stable for diff

## Usage

### Install

```bash
pnpm add -D eslint @saberwong/eslint-config
```

### Config `.eslintrc`

```json
{
  "extends": "@saberwong"
}
```

> You don't need `.eslintignore` normally as it has been provided by the preset.

### Add script for package.json

For example:

```json
{
  "scripts": {
    "lint": "eslint .",
    "lint:fix": "eslint . --fix"
  }
}
```

### Config VS Code auto fix

Install [VS Code ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) and create `.vscode/settings.json`

```json
{
  "prettier.enable": false,
  "editor.formatOnSave": false,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```

### TypeScript Aware Rules

Type aware rules are enabled when a `tsconfig.eslint.json` is found in the project root, which will introduce some stricter rules into your project. If you want to enable it while have no `tsconfig.eslint.json` in the project root, you can change tsconfig name by modifying `ESLINT_TSCONFIG` env. 

```js
// .eslintrc.js
process.env.ESLINT_TSCONFIG = 'tsconfig.json'

module.exports = {
  extends: '@saberwong'
}
```

## Extended Reading

Learn more about the context - [Why I don't use Prettier](https://saber.me/posts/why-not-prettier).

## Check Also

- [saber/dotfiles](https://github.com/saber/dotfiles) - My dotfiles
- [saber/vscode-settings](https://github.com/saber/vscode-settings) - My VS Code settings
- [saber/ts-starter](https://github.com/saber/ts-starter) - My starter template for TypeScript library
- [saber/vitesse](https://github.com/saber/vitesse) - My starter template for Vue & Vite app

## License

[MIT](./LICENSE) License &copy; 2019-PRESENT [Anthony Fu](https://github.com/saber)
