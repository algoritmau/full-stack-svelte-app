# Full-Stack Svelte App

A full-stack Svelte app, a school lunch menu CMS for school admins to publish a weekly menu for parents and students.

The app consists of a public landing page with a sign-up feature, a secured data admin page, and public lunch menu pages for a given school and week.

The app has two main parts:

- Front end: Uses Svelte to create a reactive, web-based UI

- Back end: Uses Express for CRUD operations on the app's data.

> Svelte Front-end ← API Network Calls w/ Axios → Express Back-end ← SQL Queries w/ Knex → PostgreSQL

Another tech used:

- `npm` for Package Management

- Axios for API calls

- Knex for SQL Queries

- Auth0 for JWT Authentication

## Development Environment Setup

- Node.js

- Git - For svelte project initialization

- CLI

- Text Editor

## Initializing a Svelte project

Run the following command

```bash
npx degit sveltejs/template frontend

cd frontend

npm install
```

### Set up formatting (Prettier) and linting (ESLint)

Install both extensions in VSCode

Create `.prettierrc.json`` file

```json
{
  "tabWidth": 2,
  "semi": false,
  "singleQuote": true,
  "trailingComma": "es5"
}
```

Run the following to install ESLint

```json
npm i -D eslint eslint-plugin-svelte3 @babel/core @babel/eslint-parser
```

Create `.eslintrc.json` file with the following

```json
{
  "env": {
    "browser": true,
    "es6": true,
    "node": true
  },
  "parser": "@babel/eslint-parser",
  "parserOptions": {
    "ecmaVersion": 2021,
    "sourceType": "module",
    "requireConfigFile": false
  },
  "plugins": ["@babel", "svelte3"],
  "extends": "eslint:recommended",
  "overrides": [
    {
      "files": ["**/*.svelte"],
      "processor": "svelte3/svelte3"
    }
  ]
}
```

Update npm scripts to enable linting

```json
"build": "npx eslint ./src && rollup -c"  // "build": "rollup -c",
"dev": "npx eslint ./src && rollup -c -w" // "dev": "rollup -c -w"
```

This will make ESLint to run and lint the code upon running a production build or starting the local dev env.
