# 15. Complexidade de Algoritmos

# Neste capítulo é abordado a famosa notação big-O.

Resumo do Cap. 15


## <a name="indice">Índice</a>

1. [Notação big-O](#parte1)     
2. [Notações diversas](#parte2)


## <a name="parte1">1 - Notação big-O </a>
Essa notação é utilizada para descrever o desempenho ou a complexidade de um algoritmo.
Ela é utilizada para classificar algoritmos de acordo com o tempo que eles demorarão para executar.

Considere a seguinte função: 
```
function increment(num){
    return ++num;
}
```
Se tentarmos executar essa função com increment(1), teremos um tempo de execução igua a x.
Se executarmos essa função com outro parametro, o tempo de execução também será x.
Neste caso, o parametro nao importa, o desempenho será o mesmo. Ou seja, a complexidade aqui é O(1), é constante.]

## <a name="parte2">2 - Notações diversas </a>
Assim como temos a notação constante, teremos também outras notações, variando de casa para caso, a complexidade do algoritmo muda e a notação também. 

Veja na tabela os tipos de notação possiveis:

| Notação      | Nome            |
|--------------|-----------------|
| O(1)         | Constante       |
| O(log(n))    | Logarítmica     |
| O((log(n))c) | Polilogarítmica |
| O(n)         | Linear          |
| O(n^2)       | Quadrática      |
| O(n^c)       | Polinomial      |
| O(c^n)       | Exponencial     |