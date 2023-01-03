# React Events

When adding events to an element in vanilla javascript, the `document.addEventListener` method. In JSX, events are available via their props (you can think of them as attirbutes but just don't say it out loud!).

Let's take at an example of the difference between the two. For the example below for both, we will use a simple on mouse over event to change a box from blue to red and vice versa:

```html
<div id="box" style="width:100px;height:100px;background-color:blue"></div>

<script>
  let box = document.getElementById("box");

  box.addEventListener("mouseover", function () {
    if (box.style.backgroundColor == "blue") {
      box.style.backgroundColor = "red";
    } else {
      box.style.backgroundColor = "blue";
    }
  });
</script>
```

```jsx
function App() {
  const changeBoxColor = (event) => {
    if (event.target.style.backgroundColor == "red") {
      event.target.style.backgroundColor = "blue";
    } else {
      event.target.style.backgroundColor = "red";
    }
  };

  return (
    <div
      style={{ backgroundColor: "red", width: 100, height: 100 }}
      onMouseOver={(event) => changeBoxColor(event)}
    ></div>
  );
}
```

In the JSX code, the `onMouseOver` event is exposed and we can attach a function to it and do as we please. The event param has all the same info we would get from the event param in the `document.getElementById` method.

There are other methods available for JSX. And it can be used on all elements. Yes you can append an `onClick` event to a div (it's not good practice to ALWAYS append an `onClick` onto a div but hey, you do you. If you need to append it, do it.)

Available JSX events:

- `onClick`
- `onMouseOver`
- `onMouseClick`
- `onChange` - mostly for inputs
- `onSubmit` - for forms
- and others

### Input Events

For inputs, we can easily attach functions to get the value of an input with JSX. We can use the `onChange` event to get the value.

```jsx
function App() {
  const getInputValue = (event) => {
    console.log(event.target.value); //Prints out the value of the current input
  };

  return (
    <div>
      <input name="firstName" onChange={(event) => getInputValue(event)} />
    </div>
  );
}
```

The above code only just prints out the value of the input. If we want to save the data that gets stored from the input, we would have to use state for that.

Stay tuned for the [state and lifecycle chapter](05-state-and-lifecycle.md)!
