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

In addition, although Class Components re-render whenever setState is called, Functional Components will only re-render if the state change handler causes the property to actually change.

<script>
    setSearchField("paul");
</script>

The above will only run once since once it is changed, no state change will be detected. 

## Infinite re-rendering due to requests

Sometimes requests could result in infinite re-renders. This is because of two reasons:

1. The state handler causes the state to change
2. Even if the data retrieved from the foreign API has the SAME value, the data structure returned will have a different memory address than the one before. Thus React is seeing different data being set in the state every time the request occurs. Which means it will re-render every time the request occurs. 

If the request takes place outside a hook then this will most certainly cause an infinite re-render of your app. 

# useEffect

In order to solve this issue, use the useEffect Hook. 

1. [] ensures that this code will run once and only once. Use this for data GET requests. 
2. [monsters, searchField] ensures that this code will be fire whenever the parameters are changed. Use this for data processing as you avoid having to do unecessary filters or loops (like with Class Components).

In fact this is one key advantage over the Class Components:

The code in componentDidUpdate will fire upon ANY state change. 

The code in useEffect can be used to fire upon SPECIFIC state changes. 