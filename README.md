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
<p>.map() create a new array off of one</p>
<p>double every number in an array</p>

```javascript
  const numbers = [1,2,3,4,5];
  const numbersDoubled = numbers.map(number => number * 2);
```
<p>use to create syntax</p>
```javascript
  const todosMApped = todos.map((todo, index) => (
            <div className='todo' key={index}>
              <li>{todo}</li>
              <button className='todo-button' onClick={() => removeTodoFilter(todo)}>x</button>
            </div>
          ))
```
</details>

