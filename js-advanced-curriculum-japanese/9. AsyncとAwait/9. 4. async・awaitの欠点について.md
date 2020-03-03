# `async` /` await`の欠点

`async` /` await`はコードを同期的に見せ、より同期的に動作します。`await`キーワードは、promiseが満たされるまで続くすべてのコードの実行をブロックします。
他のタスクを同時に実行し続けることはできますが、独自のコードはブロックされます。

これは、次から次へと発生するかなりの数の約束によって、コードが遅くなる可能性があることを意味します。
それぞれの`await`は、`async`/`await`を使用しなかった場合のように、実際にプロミスが同時に処理を開始することを望んでいるときに、前のものが終了するのを待ちます。

この問題を軽減するパターンがあります。変数に `Promise`オブジェクトを保存し、その後それらを待つことで、すべてのpromiseプロセスを開始できます。

```js
const delay = interval =>
  new Promise(resolve =>
    setTimeout(() => {
      console.log("done");
      resolve();
    }, interval)
  );

const test = async () => {
  await delay(3000);
  await delay(3000);
  await delay(3000);
};

test();
```

これは、3つの `delay（）`呼び出しすべてを直接待機し、各呼び出しを3秒待機させます。
これを緩和するには、次のパターンに従います。


```js
const delay = interval =>
  new Promise(resolve =>
    setTimeout(() => {
      console.log("done");
      resolve();
    }, interval)
  );

const test = async () => {
  const firstDelay = delay(3000);
  const secondDelay = delay(3000);
  const thirdDelay = delay(3000);

  await firstDelay;
  await secondDelay;
  await thirdDelay;
};

test();
```

promiseはすべて同時に処理を開始したため、同時に同時に達成され、結果を待つことができます。
