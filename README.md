# Javascript Cheat Sheet

## FETCH API
<details><summary>Fetch Api</summary>

```javascript
  const [apiData, setApiData] = useState();
  console.log('apiData', apiData);

  const getApi = async () => {
    const res = await fetch(
      'https://whateverwebsite'
    );
    const data = await res.json();
    setApiData(data);
  };

  useEffect(() => {
    getApi();
  }, []);
```
</details>

## ARRAY METHODS
<details><summary>.map()</summary>

<p>.map() creates a new array off of one</p>
<p>double every number in an array</p>

```javascript
  const numbers = [1,2,3,4,5];
  const numbersDoubled = numbers.map(number => number * 2);
```
<p>use to create syntax</p>

```javascript
  const todosMapped = todos.map((todo, index) => (
            <div className='todo' key={index}>
              <li>{todo}</li>
              <button className='todo-button' onClick={() => removeTodoFilter(todo)}>x</button>
            </div>
          ))
```
</details>

<details><summary>.forEach()</summary>

<p>.forEach() creates a loop through every index of the array</p>
<p>sum of all numbers in an array</p>

```javascript
  let sum = 0;
  numbers.forEach(number => {
    sum = sum + number;
  });
  console.log('sum', sum);
```
<p>-or-</p>

```javascript
  const getsum = (numbers) => {
    let sum = 0;
    numbers.forEach(number => {
      sum += number;
    });
    return sum;
  }
  console.log('summed', getsum(numbers))
```
</details>

<details><summary>.filter()</summary>

<p>.filter() creates a new array with filtered out objects/index</p>
<p>filter out all even numbers</p>

```javascript
  const numbers = [1,2,3,4,5,6];

  const even = numbers.filter(number => number % 2 === 0);
```

<p>filter out people over 18</p>

```javascript
  const people = [
      {
          name: 'john',
          age: 38
      },
      {
          name: 'naghmeh',
          age: 33
      },
      {
          name: 'Donny',
          age: 16
      }
  ];

  const adults = people.filter(person => person.age >= 18);
```

<p>filter out duplicate w/o Set</p>

```javascript
  const numbers = [1,2,3,4,5,6,5,4,3];
  
  const noDuplicates = numbers.filter((value, index) => {
    return numbers.indexOf(value) === index;
  });
```
<p>filter out duplicate using Set</p>

```javascript
  const numbers = [1,2,3,4,5,6,5,4,3];
  
  const noDuplicateNumbers = [...new Set(numbers)];
```
</details>

<details><summary>.sort()</summary>

<p>.sort() will sort the array how ever you tell it to</p>
<p>sort array by alphabetical order</p>

```javascript
  const months = ['March', 'Jan', 'Feb', 'Dec'];

  const sorted = months.sort();

  //sorted = ["Dec", "Feb", "Jan", "March"]
```
<p>sort array of numbers smallest to largest</p>

```javascript
  const array = [5,3,7,21,9,2,8];

  const sorted = array.sort((a,b) => a - b);

  //sorted = [2, 3, 5, 7, 8, 9, 21]
```
</details>
<details><summary>.reduce()</summary>

<p>.reduce() reduces array down using accumulator and initial value</p>
<p>sum of all numbers in an array</p>

```javascript
  const numbers = [1,2,3,4,5,6];

  const sum = numbers.reduce((accumulator, value) => {
    return accumulator + value;
  }, 0)

  //sum = 21
```

<p>return biggest number</p>

```javascript
  const numbers = [1,2,3,4,5,6];

  const max = numbers.reduce((accumulator, value) => {
    if (accumulator > value) {
      return accumulator;
    } else {
      return value;
    }
  });

  //max = 6
```
</details>

<details><summary>.includes()</summary>

<p>.includes() looks to find true/false of statement asked</p>

```javascript
  const numbers = [1,2,3,4,5,6];

  const threeExist = numbers.includes(3)

  //result = true
```
</details>

<details><summary>.some()</summary>

<p>.some() looks to find if some in an array true/false of statement asked</p>

```javascript
  const numbers = [1,2,3,4,5,6];

  const threeExist = numbers.some(numnber => number === 3)

  //result = true
```
</details>

<details><summary>.every()</summary>

<p>.every() looks to find if every in an array true/false of statement asked</p>

```javascript
  const numbers = [4,5,6];

  const greaterThanFour = numbers.every(numnber => number > 3)

  //result = true
```
</details>

## FOR LOOPS
<details><summary>For loop</summary>
<p>regular for loop set up</p>

```javascript
  let array = [];
  for(let i = 0; i < 5; i++) {
    array.push(i)
  }
```

<p>looping through existing array</p>

```javascript
  let array = [1,2,3,4,5];
  for(let i = 0; i < array.length; i++) {
    console.log(array[i]);
  }
```
</details>

## PUSH, POP, SHIFT, UNSHIFT
<details><summary>Manipulating Arrays</summary>
<p>Push - adds to end of array</p>

```javascript
  const numbers = [1,2,3,4,5];

  numbers.push(6);

  // adds 6 to end of array
```
<p>Pop - removes last item in array</p>

```javascript
  const numbers = [1,2,3,4,5];

  numbers.pop();

  // removes 5 to end of array
```
<p>unshift - adds item to beginning of array</p>

```javascript
  const numbers = [1,2,3,4,5];

  numbers.unshift(7);

  // adds 7 to beginning of array
```
<p>shift - removes item from beginning of array</p>

```javascript
  const numbers = [1,2,3,4,5];

  numbers.shift();

  // removes 1 from beginning of array
```
</details>
<details><summary>.splice()</summary>

<p>.splice() adds and or removes items in an array</p>
<p>.splice(0,0,0) first is the position, second is amount top remove, third is what to add to array</p>

```javascript
  const numbers = [1,2,3,4,5,6];

  numbers.splice(2,2)

  //at position 2 remove two items
```
```javascript
  const numbers = [1,2,3,4,5,6];

  numbers.splice(2,0, 9,10)

  //after position 2 remove no items, but add 9 and 10 to the array at that point
```
</details>
<details><summary>.slice()</summary>

<p>.slice() returns new array of selected items in an array</p>
<p>.slice(0,0) first is the position to start, second is position to stop the slice</p>

```javascript
  const numbers = [1,2,3,4,5,6];

  const newArray = numbers.slice(2,4)

  //newArray = [3,4]
```
```javascript
  const numbers = [1,2,3,4,5,6];

  numbers.splice(2,0, 9,10)

  //after position 2 remove no items, but add 9 and 10 to the array at that point
```
</details>
