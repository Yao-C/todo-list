# Start from scratch

## 1) babel 7, react 17, webpack 5, hot loading

```terminal
$ mkdir todo-list
$ cd todo-list
$ mkdir public
// add a index.html in public

$ git init   # .git
$ nano .gitignore
$ nano README.md

$ npm init   # package.json

$ npm -v   # 6.14.10   
$ sudo npm install -g npm@latest 
$ npm -v   # 6.14.11

$ node -v   # 14.15.4
$ nano .nvmrc

$ npm install --save-dev @babel/cli @babel/core @babel/preset-env @babel/preset-reac
$ nano babel.config.json

$ npm install react react-dom

$ mkdir src
// add App.css, App.js, index.js in src

$ npm install --save-dev babel-loader css-loader react-hot-loader style-loader webpack webpack-cli webpack-dev-server

// Add webpack.config.js
// Add hot babel.config.json, in Use hot in App.js
// Add scripts "dev", "build"

```
> Error: No "exports" main defined in ...
>
> Fix: npm update, 
> 'dev': webpack-dev-server to webpack serve

## 2) ESlint, prettier
```terminal
$ npm install --save-dev eslint   # "eslint": "^7.18.0"
// $ ./node_modules/.bin/eslint --init   # .eslintrc.json

// Add .eslintrc.json manually

$ nano .eslintignore
$ npm install --save-dev standard eslint-plugin-standard eslint-plugin-react

$ npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier
$ nano .prettierignore
$ nano .prettierrc

// Add scripts "lint", "lint:fix"

```

## 3) TodoList components

- NewTodoForm
- TodoList
- TodoListItem