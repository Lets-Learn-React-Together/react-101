# React 101
## Objectives
- Create your own react project
- Identify and describe the project structure
- Describe stateful and stateless components

## Creating your react project

## The Project Structure
In the root directory you'll see the following project structure:
```
> public
> src
package.json
README.json
```
### Starting at the start
Take a look at the `package.json` this is essentially the inventory or manifest of the project. Here you'll see all the dependencies (*i.e.* node modules), the scripts you can run from the command line (prefixed by `npm run`), and the name and version of the app. 

### src/
Inside the `src` directory you'll see some files with the extensions `.css` and `.js`. Let's take a look at the functions of the most important files:

- `index.js`: This is the entry point to the app. Here you'll see some imperative DOM manipulation. The App component is rendered inside of an element with the id "root". The most important thing to know here is that this is the point connecting your components to the actual HTML page.
- `App.js`: This is our first component. All other components will be rendered inside this one. You'll note this component is a functional component without state.
- `App.css`: The component-level styling. It is a convention to have `ComponentName.js` and `ComponentName.css` This would be the styling for the JSX directly inside the component
- `index.css`: The application-level styling. This would target broad things like font-faces, thematic colors, and general padding or margins.

### public/
The public file holds the html page where the app will be rendered and some relevant assets like the favicon. Most of your work will not happen in the public folder.


## Introduction to components
Components are the building blocks of React apps. They typically correspond with a portion of the UI and they follow a tree structure not unlike the DOM. Below is an example of component hierarchy:

```js
import react from 'react'
import ChildComponent from './ChildComponent'

const ParentComponent = () => {
    const name = 'some value or calculation'
    return (
        <div>
            <ChildComponent name={name} />
            {/* name would be accessible in the child component via props.name */}
        </div>
    )
}

export default ChildComponent
```

There are 2 main categories of components: **stateful** and **stateless** and they both serve different purposes. If you take a look at the App component you'll see a couple import statements at the top, a function with a long return statement, and an export statement at the bottom. Everything inside the return statement is called `JSX`. It looks, and behaves, very similar to HTML. Sometimes you may see `props` listed as a parameter or in the constructor for components. Information from parent components are passed to their children via props.

### Stateless Components
Stateless components, often called 'dumb' components or 'functional' components are pure functions. What's a pure function, you ask? Great question. A pure function takes an input and returns an output. The result is *always* the same, meaning there are no asynchronous calls. The function receives `props` and returns `JSX`

### Stateful Components
Stateful components are a bit more complex. They can be created using a es6 classes or, more recently, using functional components with `React Hooks`. For now, we'll stick with class components, because it's very likely you'll encounter them. The content that is typically in the return statement of a 'dumb' component is put inside a method called `render`.

Stateful components have a few key features we'll look into:

#### State
Component state is defined in the constructor of class components and is accessed via `this.state.<whatever you want to access>`.

```js
import react from 'React'

export default class StatefulComponent extends React.Component {
    constructor(props){
        super(props)
        this.state = {
            name: 'Dylan'
        }
    }

    render() {
        return <p>Hello {this.state.name}</p>
    }
}
```
If you need to update state, you *never* write directly to state. Instead you use the `setState` method

```js
// Good!
this.setState({name: 'Brooks'})
// Bad!
this.state.name = 'Brooks'
```


Why can't you just create an object to store state information in a 'dumb' component? There's some magic behind the `setState` method. Each time state is updated, it triggers a rerender. If you were to try and create state with an object, it wouldn't trigger a rerender and the view would never change. This also important to note because if you update state automatically from the render method you'll be stuck in a never ending loop.





