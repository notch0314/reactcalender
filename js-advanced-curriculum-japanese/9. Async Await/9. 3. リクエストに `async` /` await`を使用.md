
# **リクエストに `async` /` await`を使用**

`GET`リクエストにフェッチを使用するのは非常に簡単で、` async` / `await`を使えばよりシンプルになります。

```js
const getUser = async user => {
  const response = await fetch(`https://api.github.com/users/${user}`);
  const { name } = await response.json();
  return name;
};

getUser("yourUserNameHere").then(console.log); // 表示: Your Name
```
