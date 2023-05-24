# JSX

JSX is really just a syntax extension of JS. It allows us to write what appears to be HTML inside of JavaScript!

# setState

setState is essentially a shallow merge. This means that only the keys being passed in are updated!

This gets complicated when there is a complex object in the field and can cause errors but it forces the developer to ensure that state updates strictly follow the state structure. For example, the developer cannot update 'name' with just a string if the state structure is name: { firstName: "Yihua", lastName: "Zhang" }

# setState is Async!

This function is always asynchronous! So any code that follows it will be executed instantaneously. This is because React needs to determine how best to update the state.

If you want to have code that executes with the updated state, pass in a callback function into the parameters of the set state function:

<script>
    this.setState(
        () => {
    return { name: { firstName: "Johan", lastName: "Mihin" } };
    },
        () => {
        console.log(this.state); // will return updated state
    }
    );
</script>

# Why array keys are important

This is so that React can ensure that only the updated component will be re-rendered. This is much more efficient that re rendering the entire list of elements.

# SPA - Single Page Application

This means that we no longer need to go to the server when we navigate to different pages on the site. Since the HTML, JS and CSS was sent as a package to the browser when the page is first visited, React simply builds the different pages as they are accessed on the browser site using the JS that exists in the initial package.

# React Startup Order

This is the process React follows when it starts up an app:

1. Constructor runs before anything

- initialize the state

2. Render runs next

- set up UI

3. componentDidMount

Whenever setState is called, the render method will execute again!

# Rendering in Sub Components

Note that a component will render when:

- it first loads
- its state changes (setState is called)
- its props change (if the data passed in changes, the component will re-render)

# CSS

No matter where you import a CSS file, React will compile it into one big CSS file. So how should you structure the CSS?

- Have the CSS in the same folter as the component!

# React Hooks

## Functional Components

With this, all React does is return a function to run. Therefore it really does NOT have any lifecycles! It is simply a means of displaying data. Although Hooks can be used to REPLICATE the behavior of lifecycles.

## useState

useState, unlike setState works induvidually. So if you have multiple state values then you need multiple setState functions and vars. Each hook, hooks into one value


## rendering + re-rendering

In Class components, the whole code runs once when the component is first mounted and then the render() method runs when the state or props change. 

By contrast, functional components ALWAYS run from top to bottom since they are just functions. However, the only time it runs is when state or props change. 

