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

<details><summary>.reduce()</summary>

<p>.reduce() reduces array down using accumulator and initial value</p>
<p>sum of all numbers in an array</p>

```javascript
  const numbers = [1,2,3,4,5,6];

  const sum = numbers.reduce((accumulator, value) => {
    return accumulator + value;
  }, 0)
```
</details>


