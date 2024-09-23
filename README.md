Custom Hhooks are those which use js functions that use built in react hooks and make it reusabe logic in other components
Here's a very basic example of a custom hook that toggles a boolean value (e.g., a light switch or showing/hiding an element).

Example: useToggle Custom Hook

Step 1: Create the custom hook

import { useState } from 'react';

// Custom hook to toggle a boolean value
function useToggle(initialValue = false) {
  const [value, setValue] = useState(initialValue);

  const toggle = () => {
    setValue((prevValue) => !prevValue); // Toggle the value between true and false
  };

  return [value, toggle]; // Return the current value and the toggle function
}

export default useToggle;

Step 2: Use the custom hook in a component

import React from 'react';
import useToggle from './useToggle'; // Import the custom hook

function App() {
  // Use the custom hook to manage a toggleable state
  const [isOn, toggleIsOn] = useToggle();

  return (
    <div>
      <h1>The light is {isOn ? 'On' : 'Off'}</h1>
      <button onClick={toggleIsOn}>
        {isOn ? 'Turn Off' : 'Turn On'}
      </button>
    </div>
  );
}

export default App;

How It Works:

1. Custom Hook (useToggle):

useToggle takes an optional initial value (defaults to false if no value is provided).

It returns an array:

value: The current boolean state.

toggle: A function that toggles the value between true and false.




2. Using the Hook in the App Component:

The hook is used to control the state of a boolean (isOn) that represents whether the "light" is on or off.

The toggleIsOn function toggles this state when the button is clicked.

The text in the button and heading updates based on the current state (isOn).




Benefits:

Reusability: You can use useToggle in other components where toggling a boolean value is needed.

Simplicity: The custom hook encapsulates the toggle logic, making the component cleaner.


# Custom-Hooks
