# Key no React

## Por que única?

3 momentos em que um componente é renderizado novamente no React.

1. Quando o estado altera;
2. Quando a propriedade altera;
3. Quando um componente pai renderiza novamente.

-------------------------------------------------------------------------------

1, 2, 3, 4

1, 2, 3, 4, 5 -> o 5 não estava em tela, mais fácil para o react identificar os componentes na hora de renderizar

## Por que não posso usar o índice do array?

```js
  // const posts = [1, 2, 3, 4, 5] // pode mudar de posição
  const posts = [1, 2, 5, 4, 3] // mudou de posição
  // 0, 1, 2, 3, 4 -> índices
```