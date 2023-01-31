# Configs
### Prettier config:
```json
{
  "singleQuote": true,
  "trailingComma": "all",
  "useTabs": true,
  "semi": true,
  "bracketSpacing": true,
  "printWidth": 100,
  "endOfLine": "auto"
}
```
---
### Eslint
```json
{
  "root": true,
  "parser": "@typescript-eslint/parser",
  "plugins": [
    "@typescript-eslint"
  ],
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:prettier/recommended"
  ],
  "rules": {
    "@typescript-eslint/ban-types": "off",
    "@typescript-eslint/no-unused-vars": [
      "off"
    ],
    "@typescript-eslint/no-explicit-any": "off",
    "@typescript-eslint/explicit-function-return-type": [
      "warn"
    ],
    "prettier/prettier": [
      "error",
      {
        "singleQuote": true,
        "useTabs": true,
        "semi": true,
        "trailingComma": "all",
        "bracketSpacing": true,
        "printWidth": 100,
        "endOfLine": "auto"
      }
    ]
  }
}
```

### Eslint dependency
```json
    "@types/express": "^4.17.16",
    "@typescript-eslint/eslint-plugin": "^5.50.0",
    "@typescript-eslint/parser": "^5.50.0",
    "eslint": "^8.33.0",
    "eslint-config-prettier": "^8.6.0",
    "eslint-plugin-prettier": "^4.2.1",
```

---
### Nodemon.json
```json
{
  "watch": [
    "src"
  ],
  "ext": "ts,json",
  "ignore": [
    "src/**/*.spec.ts"
  ],
  "exec": "ts-node --files ./src/main.ts"
}
```
---
### npm scripts
```json
"scripts": {
    "start": "node ./dist/main.js",
    "dev:inspect": "nodemon -e ts,json --exec node --inspect=localhost:9229 -r ts-node/register src/main.ts",
    "lint": "eslint ./src/**",
    "lint:fix": "eslint ./src/** --fix",
    "build": "tsc",
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "nodemon"
  }
```