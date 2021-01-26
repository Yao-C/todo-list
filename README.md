# Start from scratch (A react ecosystem, from Lynda.com)

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

src/todos

- NewTodoForm
- TodoList
- TodoListItem

## 4) redux, react-redux
```terminal
$ npm i redux react-redux

// Add store.js

// Add Provider, store in src/index.js
// Add action.js in src/todos
// Add reducers.js, add reducers in store.js

// Add connect, create action in NewTodoForm.js
// Add connect, remove action in TodoList.js
// Add remove props in TodoListItem.js

```

## 5) redux-persist, add MARK action

```terminal
$ npm i redux-persist

// Add persistReducer, storage, autoMergeLevel2, redux devtools in src/store.js
// Add persistStore, PersistGate in src/index.js
// Check isCompleted in TodoListItem.js

// Add MARK action in actions.js
// Add in reducer.js
// Pass from TodoList.js
// Recived in TodoListItem.js

```

## 6) babel runtime, redux-devtools-extension, redux-thunk

```terminal
$ npm i --save-dev @babel/plugin-transform-runtime

$ npm i @babel/runtime redux-devtools-extension redux-thunk

```

- Add applyMiddleware, thunk, composeWithDevTools in src/store.js
- Add LOAD actions in actions.js
- Add loadTodos, displayAlert in thunk.js
- Add isLoading in reducers.js
- import isLoading in src/store.js

- import loadTodos, useEffect, check isLoading in TodoList.js

- Add LOADs in todos (reducers.js) 

- (actions.js) Change text to todo in createTodo 
- (reducers.js) Change text to todo (CREATE_TODO), remove newTodo 
- Change createTodo (NewTodoForm.js) to addTodoRequest (from thunks)
- import createTodo in thunks.js, add addTodoRequest

- (actions.js) Change text to todo in removeTodo 
- (reducers.js) Change text to todo (REMOVE_TODO), add id
- (thunks.js) add removeTodoRequest
- (TodoList.js) change removeTodo to removeTodoRequest, change text to id
- (TodoListItem.js) change todo.text to todo.id in onRemovePressed

- (actions.js) Change text to todo in markTodoAsCompleted
- (reducers.js) Change text to todo (MARK_TODO_AS_COMPLETED), check id
- (thunks.js) add markTodoAsCompletedRequest
- (TodoList.js) change markTodoAsCompleted to markTodoAsCompletedRequest, change text to id
- (TodoListItem.js) change todo.text to todo.id in onCompletedPressed

> Error: regeneratorRuntime is not defined
> Fix: npm i --save-dev regenerator-runtime,
> Add plugins in babel.config.json

## 7) Add selectors.js

- (store.js) Remove isLoading
- (New src/todos/selectors.js): getTodos, getTodosLoading
- (NewTodoForm.js) import getTodos from selectors
- (reducers.js) rewrite return
- (TodoList.js) import getTodosLoading from selectors

```terminal
$ npm i reselect 
```

- (selectors.js) import createSelector, add getIncompleteTodos, getCompletedTodos
- (TodoList.js) import getCompletedTodos, getIncompleteTodos

## 8) styled-components (css to js)

```terminal
$ npm i styled-components
```

- Delete App.css, NewTodoForm.css, TodoList.css, TodoListItem.css
- Add those in js as styled-components
- (TodoListItem.js) add props in styled-component
- Reuse styled-component

## 9) @babel/register, mocha, chai

```terminal
$ npm i --save-dev @babel/register mocha chai 

// Add test scripts in package.json
// Add selectors.test.js, reducers.test.js

$ npm i --save-dev node-fetch fetch-mock sinon

// Add thunks.test.js
// Add TodoListItem.test.js

```

## 10) Add server.js

```terminal
$ npm i body-parser cors express uuid
$ npm i --save-dev @babel/node

// Add server.js
// Add start script
```