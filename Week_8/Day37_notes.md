## Day 37 - 3 Nov 2020

* Read "A Complete Guide to useEffect"

## Hooks

* useContext: provides global state

## Multi-Page Functionality

* React Router - creates front-end routes so clicking between different pages causes the path to update, and visiting a path causes page to load with a particular state

## Comparing React to Other Frameworks

* Don't look at "how hot/how popular" something is, look at community support to figure out how long-lasting something will last.
* React is the top dog right now, however many devs are looking for something more light-weight
* React (VC) vs. Angular (traditional MVC)
* Flutter: mobile framework from Google
* Blazor: new Microsoft framework comparable to React
* Gatsby: server-side rendering with React components

## Common Back-end pairings with React

* Ruby on Rails
* Go/Golang
* Node/Express

## React Routers

* import BrowserRouter, Switch, & Route from react-router-dom. This helps you build a multi-page application within React e.g.
```javascript
<Router>
  <Switch>
    <Route path="/pokemon">
      <PokemonComponent>
    </Route>
    <Route exact path="/timer">
      <TimerComponent>
    </Route>
    <Route path="/">
      <ErrorPage>
    </Route>
  </Switch>
</Router>
```

Link is another component from react-router-dom, which can be done to create "links" which actually save to browser history, but don't cause a refresh (it's all client-side scripting to render the new page)
```js
<Link to="/pokemon">pokemon</Link>
```
* *useParams* hook allows you to access :id params from the URL like in Express

## Travis's Tips

* *screens* folder: make one for a page, and place components onto that page. A good way of preventing all your routes from clogging up your main app.js page
* Place the routes in each screens file in an array, and then use the spread operator to put them into one big array in the main component <Application>

## Context

* by convention, we throw these in a separate folder called "context"
```js
import { createContext } from React;
const dogContext = createContext(['Rufus','Lupus','Fluffy']);
// This is the source of our single global state
export default dogContext;

```

* Then in a different file:

```js
import React, { useContext } from React;
import dogContext from '../contexts/dogContext';

const Dogs = () => {
  const dogList = useContext(dogContext);
  return (
    <div>
      dogList.map((dog) => {
        return <h2>{dog.name}</h2>
      });
    </div>
  )
}
```