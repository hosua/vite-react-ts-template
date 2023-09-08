# React + TypeScript + Vite template

This repository is a template that will serve me as a reminder for me on how to get auto formatting working with a fresh React + TypeScript + Vite project.

If things dont work out after following my guide, this [guide](https://andrebnassis.medium.com/setting-prettier-on-a-react-typescript-project-2021-f9f0d5a1d6b0) is what fixed everything.

### Setup instructions

Here are the instructions to set up an app named `foo` with auto-formatting working on vscode from start to finish:

`npm create vite@latest foo`

Select `React`

Select `TypeScript` or `TypeScript + SWC` (SWC is supposedly faster)

Run `npm install --save-dev prettier eslint-config-prettier`

Create a file named: `.prettierrc.json` in the project's root directory with the following contents. If one is not provided, prettier will still work with some default settings. You can change these settings to suit your preferences.

```json
{
  "trailingComma": "all",
  "tabWidth": 2,
  "singleQuote": true,
  "jsxBracketSameLine": true
}
```

In `package.json` of the project root, add the configurations:

```json
"eslintConfig": {
  "extends": [
    "react-app",
    "react-app/jest",
    "prettier"
  ]
},
```

Now in vscode, make sure that the [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) extension is installed.

Do not confuse this with [Prettier ESLint](https://marketplace.visualstudio.com/items?itemName=rvest.vs-code-prettier-eslint)! This was not working for me at the time of writing this README.

The extension ID for `Prettier - Code formatter` is `esbenp.prettier-vscode`.

So now in `.vscode/settings.json`, you should have the following contents to enable auto-formatting on save:

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode"
}
```

Alternatively in the GUI, you can press `Ctrl+shift+p` and select `Preferences: Open Workspace Settings`.

In here, search for `Default Formatter` and choose `Prettiewr - Code formatter` as the default formatter.

After that, search for `Format On Save` and check the box.

This should produce the same `.vscode/settings.json` above after choosing the settings.
