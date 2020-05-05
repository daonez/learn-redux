# Vanilla Redux

### NomadCoder Redux part 1

```javascript
//@ Vanilla JS Counter + Redux

import { createStore } from "redux";

//*vanilla DOM
const add = document.getElementById("add");
const minus = document.getElementById("minus");
const number = document.getElementById("span");

const ADD = "ADD";
const MINUS = "MINUS";
//* Reducer
const countModifier = (count = 0, action) => {
  switch (action.type) {
    case ADD:
      return count + 1;
    case MINUS:
      return count - 1;
    default:
      return count;
  }
};
const countStore = createStore(countModifier);

//*Subscribe
const onChange = () => {
  number.innerText = countStore.getState();
  console.log(countStore.getState());
};
countStore.subscribe(onChange);

//* connecting actions to button
add.addEventListener("click", () => countStore.dispatch({ type: ADD }));
minus.addEventListener("click", () => countStore.dispatch({ type: MINUS }));
```

![counter](https://github.com/daonez/learn-redux1/blob/master/src/gif/counter.gif?raw=true)
