# Intro to react

### What is React?

React is a Javascript Library that focuses on creating User Interfaces. It's an open-source, component-based front-end library responsible only for the view layer of an application.
It also focuses on Reusability with components. That way you are not constantly rewriting parts of your UI over and over.

### How do I use React?

React uses something called JSX as the main markup in order to make the User Interfaces while completely using Javascript to write the functionality.

#### What is JSX?

According to the React Documentation, "...it is a syntax extension to JavaScript. We recommend using it with React to describe what the UI should look like. JSX may remind you of a template language, but it comes with the full power of JavaScript." It looks like this:

```JSX
  //Simple JSX element
  const element = <h1>Hello world</h1>;
```

Notice that JSX looks **EXACTLY** like HTML but please do not confuse it with HTML...cause it's not HTML. (We will talk about the differences later)

#### React Components

React components are made up of a bunch of JSX elements. You can create your own components using React or use some third party made components. As long as the component returns JSX, that's all that matters.

Simple Component:

```JSX
  //This is a navbar
  //Does not need the name of Navbar component. Components can be named whatever you want
  function NavbarComponent(){
    return (
      <div className="navbar"> //Assume that the classes already exist
        <ul className="navbar-list">
          <li className="navbar-item">Home</li>
          <li className="navbar-item">About</li>
          <li className="navbar-item divider"></li>
          <li className="navbar-item">Login</li>
        </ul>
      </div>
    )
  }
```

Now if you want to plug it into a page in React, you can write:

```JSX
function NavbarComponent(){
  //Code for the component above
}

function HomePage(){
  return (
    <div className="home-page">
      <NavbarComponent />
    </div>
  )
}

```

Ok so that was alot of code but that will be explained in the 02-Components

#### So then what are the differences between HTML and JSX?

| HTML                                                                                                                                                         | JSX                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------- |
| Has Attributes                                                                                                                                               | Uses Props                                                                                                                         |
| It is not necessary to use camelCase for attributes, ids and event references. Its totally your call to use camelCase, lowercase or hyphens for naming them. | All HTML attributes and event references in JSX become camelCase, this way, onclick event becomes onClick and onchange — onChange. |
| Tags mostly close with their own tag. Example: `<div></div>`                                                                                                 | JSX elements can be self closed or closed with their own tag. Example of Self closing: `<div />`                                   |
|                                                                                                                                                              | Uses `className` to connect to CSS classes                                                                                         |

There are other differences but these are the main differences.

Next lets look more into details of Components and using it. Click [here](02-components.md) for the next chapter.
