# React Core Concepts

## React will NOT touch the DOM

In the past, an Imperative Paradigm governed app display interaction. This involves using JS to directly change the DOM according to the app logic. 

React uses a Declarative Paradigm. Since changing the DOM is usually a very resource intesive task, React determines the optimum way to perform this task and simply asks the developer what the required change is through its logic. 

As such, the dev code will NEVER touch the DOM itself due to React being the middle-man. 

## Re-usable Components

This involves creating many reusable components which can be used over and over again with induvidual sets of data. Websites are built like lego blocks. 

## Uni-directional data-flow

Any time we want something to change in our website, the state needs to change. Data flows from the state to the Virtual DOM and then finally to the actual DOM. Therefore if there is an error in the app, the only place to look is the React Component itself! There is no need to look at the DOM tree. 

# Why use npx?

Npx installs create-react-app, uses it to build the scaffolding for the app, and then uninstalls it from the global directory. 

Npx can be used outside of simply create-react-app too!

# Software Leveraged for Build

- Webpack: chunks your JS into component or page specific pieces so that the page only loads that specific piece of code for that part of the app. 
- Babel: transpiles all your JS into a version all browsers can understand

