# Javascript Cheat Sheet

<details><summary>FETCH API</summary>

#### Fetch Api

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
