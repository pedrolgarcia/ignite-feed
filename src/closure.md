# Closures no React

```js
function Comment(props) {
  const [likeCount, setLikeCount] = useState(0);

  function addLike() {
    setLikeCount(likeCount + 1);

    // Não funciona, vai continuar atualizando de 1 em 1
    // Isso porque o React ainda está trabalhando no mesmo contexto, logo, durante essas novas execuções o valor de likeCount vai ser sempre o mesmo
    setLikeCount(likeCount + 1); // => 0 + 1 = 1
    setLikeCount(likeCount + 1); // => 0 + 1 = 1
    setLikeCount(likeCount + 1); // => 0 + 1 = 1
    setLikeCount(likeCount + 1); // => 0 + 1 = 1
    setLikeCount(likeCount + 1); // => 0 + 1 = 1

    // Soluções:
    // Sempre que você for atualizar uma informação, e essa informação depende dela mesma (do valor que ela tinha anteriormente), atualize o estado utilizando um dos padrões abaixo
    // 1.
    setLikeCount((oldState) => {
      // => 0 + 1 = 1
      return oldState + 1;
    });
    setLikeCount((oldState) => {
      // => 1 + 1 = 2
      return oldState + 1;
    });

    // 2.
    var newLikeCount = likeCount + 1;
    setLikeCount(newLikeCount + 1); // => 0 + 1 = 1
    setLikeCount(newLikeCount + 1); // => 1 + 1 = 2
  }
}

Comment(props, 0);

Comment(props, 1);
```
