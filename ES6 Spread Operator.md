# ES6 Spread Operator

Language: `JavaScript`

## Info

ES6 provides a new operator called spread operator that consists of three dots (**...**). The spread operator allows you to spread out elements of an iterable object such as an array,a map, or a set.

- Basic Working of snippet
- use **...** insead anything else if you want to use one array into to another array
- For Example:

  ```
  let arr1 = [1, 2, 3];
  let arr2 = [4, 5, 6];
  arr2 = [...arr1, 4, 5, 6];
  console.log(arr2);

  ```

- Its save lost of time if you are working with react.

## Code

```
import React, { useState } from "react";

function App() {
  const [contact, setContact] = useState({
    fName: "",
    lName: "",
    email: "",
  });

  function handleChange(event) {
    const { value, name } = event.target;


   setContact((prevalue) => {
       return {
            ...prevalue,
            [name]: value,
   })


// See Difference between setContact with spread operator or without it

    setContact((prevalue) => {

      if (name === "fName") {
        return {
          fName: value,
          lName: prevalue.lName,
          email: prevalue.email,
        };
      } else if (name === "lName") {
        return {
          fName: prevalue.fName,
          lName: value,
          email: prevalue.email,
        };
      } else if (name === "email") {
        return {
          fName: prevalue.fName,
          lName: prevalue.lName,
          email: value,
        };
      }
    });
  }

  return (
    <div className="container">
      <h1>
        Hello {contact.fName} {contact.lName}
      </h1>
      <p>{contact.email}</p>
      <form>
        <input
          name="fName"
          onChange={handleChange}
          value={contact.fName}
          placeholder="First Name"
        />
        <input
          name="lName"
          onChange={handleChange}
          value={contact.lName}
          placeholder="Last Name"
        />
        <input
          name="email"
          onChange={handleChange}
          value={contact.email}
          placeholder="Email"
        />
        <button>Submit</button>
      </form>
    </div>
  );
}

export default App;


```

## Usage

```

//Just Add (...) and name of array
//code
 ...array

```
