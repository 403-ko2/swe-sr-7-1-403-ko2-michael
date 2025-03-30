# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

In your own words, explain why React is a popular choice for building user interfaces. Make sure to mention at least one benefit, such as how it simplifies development, supports reusable components, or helps optimize performance. Feel free to include any specific features you find particularly helpful.

### Response 1

React is a javaScript library and is popular for a multitude of reasons when it comes to building user interfaces. React combines HTML and javaScript together making it possible to create an interface a lot faster and more efficient than if you were to use the two seperatly. Its like putting together a jigsaw puzzle where each piece of the puzzle is a component made in react that is later put together to create a final product. To dive deeper into this, react allows you to return html elements in the same file where you would utilize those elements with javaScript, knocking out two birds with one stone. React also gives you access to hooks which will be discussed in the following questions.

## Prompt 2

Explain how the useState hook is used in React to manage state within functional components. In your response, include an example of how useState might be used in a simple application and why managing state is important in building interactive user interfaces.

### Response 2

The useState hook allows functional components to manage its data (state) as well as update its data locally without needing class components. To do this it takes in an initial value as an argument, and returns an array with two elements, a 'variable' and a setter function to 'update' that 'variable' whenever the setter function is called it re-renders with the data (state) updated, an example is shown below:

```jsx
import { useState } from 'react';

function Counter() {
	// Declare a state variable 'count' initialized to 0
	const [count, setCount] = useState(0);

	return (
		<div>
			<h1>Counter: {count}</h1>
			<button onClick={() => setCount(count + 1)}>Increment</button>
			<button onClick={() => setCount(count - 1)}>Decrement</button>
			<button onClick={() => setCount(0)}>Reset</button>
		</div>
	);
}

export default Counter;
```

## Prompt 3

Describe the different ways the useEffect hook can be triggered in a React component. Include an explanation of how the dependency array influences its behavior. If possible, provide a code example for each scenario to illustrate your explanation.

### Response 3

## Prompt 4

The component below makes a mistake when using useEffect. When running this code, we will get an error from React! Please fix this code.

```js
const DogDisplay = () => {
  const [imgSrc, setImgSrc] = useState('https://images.dog.ceo/breeds/hound-english/n02089973_612.jpg');

  useEffect(async () => {
    try {
      const response = await fetch('https://dog.ceo/api/breeds/image/random');
      if (!response.ok) throw new Error(`Error: ${response.status}`)
      const data = await response.json();
      setImgSrc(data.message);
    } catch (error) {
      console.error(error);
    }
  }, []);

  return <img src={imgSrc} />
}
```

After fixing the code provide and explanation to what you fixed and why it needed to be fixed.

### Response 4
