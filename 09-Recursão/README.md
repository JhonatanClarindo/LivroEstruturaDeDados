# 9. Recursão

# O capítulo explica e exemplifica sobre as funções recursivas e como podem ser usadas para resolver problemas.

Resumo do Cap. 09


## <a name="indice">Índice</a>

1. [Introdução à recursividade](#parte1)     
2. [Exemplo sequência de Fibonacci](#parte2)     
3. [Exemplo de pesquisa binária](#parte3)

## <a name="parte1">1 - Introdução à recursividade </a>

Recursão é uma técnica usada para resolver problemas que podem ser dividos em subproblemas menores e semelhantes. As funções recursivas, geralmente têm um caso base e um caso recursivo. O caso base é a condição que interrompe a recursão, enquanto o caso recursivo é a condição que continua a recursão.

O capítulo cobre varios exemplos de recursão, são eles:

## <a name="parte2">2 - Exemplo sequência de Fibonacci </a>

A sequência de Fibonacci é uma série de números em que cada numero é a soma dos dois numeros anteriores, começando em 0 e 1.
Pode-se calcular o n-ésimo número na sequência de Fibonacci usando a seguinte função recursiva:

```
function fibonacci(n) {
  if (n === 0 || n === 1) {
    return n;
  } else {
    return fibonacci(n - 1) + fibonacci(n - 2);
  }
}

```

## <a name="parte3">3 - Exemplo de pesquisa binária </a>
Os algoritmos de pesquisa binária também são conhecidos como pesquisa de meio intervalo. Eles retornam a posição do valor pesquisado em uma lista classificada. Esses algoritmos usam a técnica de "dividir para conquistar" para encontrar a posição do valor.
O algoritmo pode ser implementado, dividindo a matriz ao merio e verificando se o valor está na metade esquerda ou na metade direita.

Veja como  ficaria a função recursiva implementada:

```
function binarySearch(arr, value, start, end) {
  if (start > end) {
    return -1;
  }
  const mid = Math.floor((start + end) / 2);
  if (arr[mid] === value) {
    return mid;
  } else if (arr[mid] > value) {
    return binarySearch(arr, value, start, mid - 1);
  } else {
    return binarySearch(arr, value, mid + 1, end);
  }
}

```

A função primeiro verifica se o start índice é maior que o end índice. Se esta condição for verdadeira, significa que o valor não foi encontrado dentro do array, então a função retorna -1.

Se o start índice for menor ao end índice, a função calculará o mid índice tomando a média dos índices start e end, arredondando para o número inteiro mais próximo usando o método Math.floor.

Se o value no mid índice do arr array corresponder ao que value está sendo procurado, a função retorna o mid índice.

Se o value no mid índice for maior do que o value que está sendo procurado, a função faz uma chamada recursiva para binarySearch com a mesma matriz, o mesmo value e um novo end índice de mid - 1, estreitando efetivamente o intervalo de pesquisa para a metade esquerda da matriz.

Se o value no mid índice for menor que o que value está sendo procurado, a função faz uma chamada recursiva para binarySearch com o mesmo arr, o mesmo value, e um novo start índice de mid + 1, estreitando efetivamente o intervalo de pesquisa para a metade direita do array.

A função continua a dividir recursivamente o intervalo de pesquisa pela metade até que seja value encontrado ou até que o start índice se torne maior que o end índice. Nesse ponto, a função retorna -1 para indicar que o valor não foi encontrado na matriz.