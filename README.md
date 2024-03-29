# VSCode configuration + Eslint + Prettier

## Install ESLint plugin for VScode

https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint

## Install Prettier plugin for VScode

https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode

## Create your folder

```
mkdir myfolder
cd myfolder
```

## Init folder with npm

```
npm init -y
```

## Install npm package needed

Basics

```
npm install --save-dev eslint eslint-plugin-prettier eslint-config-prettier prettier eslint-plugin-promise eslint-plugin-imports eslint-plugin-node
```

With html support + babel-eslint

```
npm install --save-dev babel-eslint eslint eslint-plugin-prettier eslint-config-prettier prettier eslint-plugin-promise eslint-plugin-imports eslint-plugin-node eslint-plugin-html
```

With airbnb config html support + babel-eslint

```
npm install --save-dev babel-eslint eslint eslint-plugin-prettier eslint-config-prettier prettier eslint-plugin-promise eslint-plugin-imports eslint-plugin-node eslint-plugin-html eslint-config-airbnb-base
```

With standard config html support + babel-eslint

```
npm install --save-dev babel-eslint eslint eslint-plugin-prettier eslint-config-prettier prettier eslint-plugin-promise eslint-plugin-imports eslint-plugin-node eslint-plugin-html eslint-config-standard eslint-plugin-standard
```

With standard config html support + babel-eslint + webpack

```
npm install --save-dev babel-eslint eslint eslint-plugin-prettier eslint-config-prettier prettier eslint-plugin-promise eslint-plugin-imports eslint-plugin-node eslint-plugin-html eslint-config-standard eslint-plugin-standard eslint-import-resolver-webpack
```

## Create .eslintrc file

Configuration basics with airbnb-config

```
{
  "parserOptions": {
    "ecmaVersion": 6,
    "sourceType": "module"
  },
  "extends": ["airbnb-base", "plugin:prettier/recommended"],
  "rules": {
    "no-unused-vars": 1,
    "no-multiple-empty-lines": 2,
    "no-console": ["error", { "allow": ["warn", "log"] }]
  },
  "env": {
    "browser": true
  },
  "settings": {}
}
```

Configuration with babel + plugin html + config airbnb

```

{
"parser": "babel-eslint",
"parserOptions": {
"ecmaVersion": 6,
"sourceType": "module"
},
"extends": ["airbnb-base", "plugin:prettier/recommended"],
"plugins": ["html"],
"rules": {
"no-unused-vars": 1,
"no-multiple-empty-lines": 2,
"no-console": ["error", { "allow": ["warn", "log"] }]
},
"env": {
"browser": true,
"es6": true,
"node": true
},
"settings": {}
}

```

Configuration with babel + plugin html + config standard

```

{
"parser": "babel-eslint",
"parserOptions": {
"ecmaVersion": 6,
"sourceType": "module"
},
"extends": ["standard", "plugin:prettier/recommended"],
"plugins": ["html"],
"rules": {
"no-unused-vars": 1,
"no-multiple-empty-lines": 2,
"no-console": ["error", { "allow": ["warn", "log"] }]
},
"env": {
"browser": true,
"es6": true,
"node": true
},
"settings": {}
}

```

## Create .prettierc config file

```

{
"singleQuote": true,
"trailingComma": "all"
}

```

## User Settings VSCode

Modify settings
Code > Preferences > Settings

```

"editor.formatOnSave": true,
"[javascript]": {
"editor.formatOnSave": false
},
"eslint.autoFixOnSave": true,
"eslint.alwaysShowStatus": true,
"prettier.disableLanguages": [
"js"
],
"prettier.eslintIntegration": true

```

## Lint Script

Include new script in package.json to run ESLint

```

"lint": "eslint src -c .eslintrc --ext js,jsx",

```

## Ignoring files

Create a .eslintignore file

```

node_modules/_
public/_
dist/_
config/_

```

```

```
