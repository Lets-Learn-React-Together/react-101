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

### The code
Inside the `src` directory you'll see some files with the extensions `.css` and `.js`. Let's take a look at the functions of the most important files:

- `index.js`: This is the entry point to the app. Here you'll see some imperative DOM manipulation. The App component is rendered inside of an element with the id "root". The most important thing to know here is that this is the point connecting your components to the actual HTML page.
- `App.js`: This is our first component. All other components will be rendered inside this one. You'll note this component is a functional component without state.
- `App.css`: The component-level styling. It is a convention to have `ComponentName.js` and `ComponentName.css` This would be the styling for the JSX directly inside the component
- `index.css`: The application-level styling. This would target broad things like font-faces, thematic colors, and general padding or margins.


### Handy things to know
- Babel
- ReactDOM
- Webpack
- Node modules
- Components
