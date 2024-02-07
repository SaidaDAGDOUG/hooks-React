# Hooks Exemple:  

## Overview:

This is an exmple from Coursera course "React Basics" is part of the Coursera course "Introduction to iOS Mobile Application Development."  
You will learn how to use hooks in React components and understand the use-cases for the useState hook.  

## Description:  
Let’s say you have a component with an input text field. The user can type into this text field.  
The component needs to keep track of what the user types within this text field. You can add state and use the useState hook, to hold the string.  
As the user keeps typing, the local state that holds the string needs to get updated with the latest text that has been typed.  
Let's discuss the below example.  

 ```bash
    import { useState } from 'react';
    
    export default function InputComponent() { 
      const [inputText, setText] = useState('hello'); 
    
      function handleChange(e) { 
        setText(e.target.value); 
      } 
    
      return ( 
        <> 
          <input value={inputText} onChange={handleChange} /> 
          <p>You typed: {inputText}</p> 
          <button onClick={() => setText('hello')}> 
            Reset 
          </button> 
        </> 
      ); 
```

To do this, let's define a React component and call it InputComponent. This component renders three things:  

- An input text field.  
- Any text that has been entered into the field.   
- A Reset button to set the field back to its default state.   
<img width="198" alt="Screenshot 2024-02-06 at 11 48 43 PM" src="https://github.com/SaidaDAGDOUG/hooks-React/assets/92460033/8d65d6c3-56e0-42af-9a23-d7677042b9d9">

As the user starts typing within the text field, the current text that was typed is also displayed.

The state variable inputText and the setText method are used to set the current text that is typed. The useState hook is initialized at the beginning of the component.  

```bash
    const[inputText, setText] = useState('hello');
```
By default, the inputText will be set to “hello”.

As the user types, the handleChange function, reads the latest input value from the browser’s input DOM element, and calls the setText function, to update the local state of inputText.  
```bash
   function handleChange(e) {
    setText(e.target.value);
};
```
Finally, clicking the reset button will update the inputText back to “hello”.   

Isn’t this neat?  

Keep in mind that the inputText here is local state and is local to the InputComponent. This means that outside of this component, inputText is unavailable and unknown. In React, state is always referred to the local state of a component.  
the useState hook that you just learned.  
Hooks also come with a set of rules, that you need to follow while using them. This applies to all React hooks, including the useState hook that you just learned.  
  - You can only call hooks at the top level of your component or your own hooks.   
  - You cannot call hooks inside loops or conditions. 
  - You can only call hooks from React functions, and not regular JavaScript functions. 
