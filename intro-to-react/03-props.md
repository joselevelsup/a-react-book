# Props

## What are Props?

In React, we are going to want to pass data from one component to another or we just want to set data for the component by default when it's mounted. For that, we use `props`!

Props are short for Properties. When creating a component can have different types of props. **By default. props are an empty object until you add a prop onto the component**

Example:

```jsx
function Component1(props) {
  //Going to print out as {}
  console.log(props);

  return <div></div>;
}

//Cause the component currently has no props on it
<Component1 />;
```

Now once you add a prop onto a component, then props will contain some data based on what you passed.

Example:

```jsx
function Component1(props) {
  //Going to print out as { name: "Name" }
  console.log(props);

  return <div></div>;
}

//Cause the component currently has nothing
<Component1 name="Name" />;
```

So now with the component has a prop, the component can now use that prop. Before then, let's talk about evaluating javascript in JSX.

**Props do not only need to be evaluated. They can also be utilized in other functions or variables in the component**

### Evaluating Javascript in JSX

In order for Javascript to run in JSX, we can use curly brackets in the JSX.

Example:

```jsx
//Using a string
const name = "Name here";
const SimpleHeader2 = <h2>{name}</h2>;

const todos = [
  {
    id: 1,
    task: "Give dog bath",
  },
  {
    id: 2,
    task: "Buy the groceries",
  },
];

const TodoList = (
  <ul>
    {todos.map((todo) => (
      <li>{todo.task}</li>
    ))}
  </ul>
);
//The above would be rendered as
// <ul>
//  <li>Give dog bath</li>
//  <li>Buy the groceries</li>
// </ul>
```

We can run functions, use variables, loop through items, and so much more. It's similar to the way props are used

### Evaluating React props in JSX

Example:

```jsx
function Component1(props) {
  //Going to print out as { name: "Name" }
  console.log(props);

  //returns <div>Name</div>
  return <div>{props.name}</div>;
}

//OR

//Using object destructuring
function Component1({ name }) {
  //returns <div>Name</div>
  return <div>{name}</div>;
}

//Cause the component currently has nothing
<Component1 name="Name" />;
```

With props, you can pass anything into a component's props

Example:

```jsx
function Component1(props) {
  //prints {
  // name: "Name",
  // arr: [//items of array here],
  // }
  console.log(props);

  //jsx return statement below
}

<Component1
  name="Name"
  arr={
    [
      /*items in here*/
    ]
  }
/>;
```

Let's edit the navbar component with a list of links that can be navigated to different pages (**This code is using the code from the the components chapter**):

```jsx
function Navbar(props) {
  return (
    <div className="navbar">
      <ul className="navbar-list">
        {props.links.map((link) => (
          <li className="navbar-item">
            <a href="#">{link}</a>
          </li>
        ))}
      </ul>
    </div>
  );
}

function App() {
  return (
    <div className="app">
      <Navbar links={["Home", "About"]} />
      <div className="page-content">
        <Sidebar />
        <div className="content">
          <MyCoolButton />
          <MyCoolButton />
          <MyCoolButton />
        </div>
      </div>
    </div>
  );
}
```

In the code above, We edited the code to the Navbar component to accept props and added the `links` prop. Now in the JSX, we are able to use the curly brackets to evaluate some javascript (in this case, a `map`) and use the data in the array which is just the string in the array. This enables us to be a little lazy with how we can write out the items in the navbar by just passing a simple array or strings.

In the next chapter, we will be talking about [events](04-events.md)
