# react-parcel-tooling-setup

tooling setup for a react application taking into account
code quality,routing and hooks

## Code Quality

run `npm install -D prettier` where -D means for development only.
Add `"format": "prettier --write \"src/**/*.{js,jsx}\"",` to your scripts file to to releave you from running the long command every time
.If you are using visual studio code..you can go to extensions and install prettier.it is in the view->extensions->(search for prettier)  
Lastly,set `prettier.requireConfig` to true and ``editor.formatOnSave``` to true in settings .Create a file called .prettierrc and put {} in it.

.......................
Next we are going to setup ESLint.`npm install -D eslint eslint-config-prettier`
Create a file called `.eslintrc.json`. and add `"lint": "eslint \"src/**/*.{js,jsx}\" --quiet"`, to your script file

## git

create `.gitignore` file and add the following

````node_modules
.cache/
dist/
.env
.DS_Store
coverage/
.vscode/ ```

##  parcel
to add parcel do: ```npm install -D parcel-bundler``` and add ```"dev": "parcel src/index.html"``` to your scripts file

## react
for react and react dom do ```npm install react react-dom```
to configure eslint to work with react ```npm install -D babel-eslint eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react```
then update eslint to look like:
````

{
"extends": [
"eslint:recommended",
"plugin:import/errors",
"plugin:react/recommended",
"plugin:jsx-a11y/recommended",
"prettier",
"prettier/react"
],
"rules": {
"react/prop-types": 0
},
"plugins": ["react", "import", "jsx-a11y"],
"parserOptions": {
"ecmaVersion": 2018,
"sourceType": "module",
"ecmaFeatures": {
"jsx": true
}
},
"env": {
"es6": true,
"browser": true,
"node": true
},
"settings": {
"react": {
"version": "detect"
}
}
}```

to add eslint rules for hooks do `npm install -D eslint-plugin-react-hooks`
and then add to .eslintrc.json file this: `{ "rules": { …, "react-hooks/rules-of-hooks": "error" }, "plugins": [ …, "react-hooks" ], }`

## routing

for routing use reach router ...``npm install @reach/router`by Ryan alternatively use react router

## babel

Lastly to use class properties and take control of babel do :`npm install -D babel-eslint @babel/core @babel/preset-env @babel/plugin-proposal-class-properties @babel/preset-react```
then add the folowing to a .babelrc file you create:

````
and add ```  "parser": "babel-eslint",``` to eslint file
## css
for css use tools like emotion or styled components which are actually compatible...we are going to use emotion ```npm install @emotion/core @emotion/babel-preset-css-prop``` and add the following to the .babelrc file ``` [
      "@emotion/babel-preset-css-prop",
      {
        "sourceMap": false
      }
    ]```
````
