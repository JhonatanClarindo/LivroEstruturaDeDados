# 3. Arrays
## O capítulo 3 explica como usar a estrutura de dados mais básica e mais utilizada, os arrays. 
Resumo do Cap. 03

## <a name="indice">Índice</a>

1. [Por que devemos usar arrays?](#parte1)     
2. [Criando e inicializando arrays](#parte2)     
3. [Acessando elementos e iterando em um array](#parte3)     
4. [Acrescentando elementos](#parte4)     
5. [Usando o método push](#parte5)     
6. [Inserindo um elemento na primeira posição](#parte6)     
7. [Usando o método unshift](#parte7)     
8. [Removendo elementos](#parte8)     
9. [Removendo um elemento da primeira posição](#parte9)     
10. [Usando o método shift](#parte10)     
11. [Acrescentando e removendo elementos de uma posição específica](#parte11)     
12. [Arrays bidimensionais e multidimensionais](#parte12)     
13. [Iterando pelos elementos de arrays bidimensionais](#parte13)     
14. [Arrays multidimensionais](#parte14)     
15. [Referências para métodos de array em JavaScript](#parte15)     
16. [Juntando vários arrays](#parte16)     
17. [Funções de iteração](#parte17)     
18. [Iterando com o método every](#parte18)     
19. [Iterando com o método some](#parte19)     
20. [Iterando com forEach](#parte20)     
21. [Usando map e filter](#parte21)     
22. [Usando o método reduce](#parte22)     
23. [ECMAScript 6 e novas funcionalidades de Array](#parte23)     
24. [Iterando com o laço for..of](#parte24)     
25. [Ordenando elementos](#parte25)     
26. [Convertendo um array em uma string](#parte26)     
27. [Classe TypedArray](#parte27)     
28. [Resumo](#parte28)     
---


## <a name="parte1">1 - Por que devemos usar arrays? </a>

Um array é a estrutura de dados mais simples possível em memória. Um array armazena valores que são todos do mesmo tipo, sequencialmente. EMbora o JS nos permita esse tipo de peripécia, partiremos do pressuposto de que não podemos fazer isso e obedeceremos as melhores práticas.


[Voltar ao Índice](#indice)

---

## <a name="parte2">2 - Criando e inicializando arrays</a>

A forma mais prática e comum de se criar um array é atribuir um colchete vazio.
```
let daysOfWeek = []
```
Para saber o tamanho de um array, basta utilizar .length, veja:

```
console.log(daysOfWeek.length);
```

[Voltar ao Índice](#indice)

---


## <a name="parte3">3 - Acessando elementos e iterando em um array</a>

Um array trabalha com indices. Resumidamente, cada elemento possui uma casa que assim como uma casa comum, possui um numéro. Essa "casa" é chamada de indice e pode ser acessada. __É importante se ter em mente que em computação, uma sequencia de numéros se inica no zero, logo, o primeiro indice de um array é zero__
Caso, queria-se acessar a terceira "casa" do array daysOfWeek, o seguinte código seria executado:

```
console.log(daysOfWeek[2])
```
_Para dar um pequeno grau de complexidade em nosso exemplo, podemos percorrer todos os indices de um array com um laço for. Veja:_

```
for(let i = 0; i < daysOfWeek.length; i++) {
    console.log(daysOfWeek[i])
}

```
[Voltar ao Índice](#indice)

---


## <a name="parte4">4 - Acrescentando elementos</a>

A partir deste ponto até o tópico 11, iremos tratar de remoção e insersão de elementos em um array. Para isso, vamos considerar o array:

let numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

[Voltar ao Índice](#indice)

---

## <a name="parte5">5 - Usando o método push</a>

O JS possui um método que nos permite adicionar novos elementos __AO FINAL__ do array. O método push. Veja:

```
numbers.push(11, 12, 13)

```
O array exibirá elementos de 0 a 13 na saída
[Voltar ao Índice](#indice)

---


## <a name="parte6">6 - Inserindo um elemento na primeira posição </a>

Imagine que temos que adicionar um elemento na primeira posição do array. Para que isso seja posivel, o primeiro passo seria deslocar todos os elemento para a direita, fazendo assim que a primeira posição fique livre. Para isso iremos percorrer todos os elementos do array com um laço, começando pela última posição, deslocando o elemento da sua posição antiga para a nova. Por fim, faremos a atribuição do valor desejado à primeira posição. Podemos fazer tudo isso com uma função e até mesmo usar o array.prototye. O código abaixo mostra como toda essa novela ocorreria. 

```
array.prototype.insertFirtsPosition = function(value) {
    for (let i = this.length; i >= 0; i++) {
        this[i] = this[i - 1]
    }
    this[0] = value
}
 numbers.insertFirstPosition(-1)
```
Esse exemplo todo poderia ter sido ignorado, mas achei interessante deixar ele aqui para servir de exemplo que com a lógica correta, podemos executar diversas peripécias com o JS. Entretanto, nao iremos precisar sofrer tanto para tal feito, pois temos um método perfeito para isso. Segue o baile...
[Voltar ao Índice](#indice)

---


## <a name="parte7">7 - Usando o método unshift </a>

Anteriormente, vimos a função que pode ser inserir um elemento em um array, porém, uma benção divína cai sobre nós e toda a função pode ser substituida pelo seguinte código:

```
numbers.unshift(-2, -1)

```

[Voltar ao Índice](#indice)

---

## <a name="parte8">8 - Removendo elementos</a>

Para remover um elemento do array, o livro também usa como exemplo um laço for dentro e uma função e etc...entretadno, o objetivo deste arquivo é o resumo. Por isso, não entrarei em detalhes sobre a remoção do elemento por função e iremos direto ao ponto com os métodos, pop(), shift() e splice()

[Voltar ao Índice](#indice)

---


## <a name="parte9">9 - Removendo um elemento da última posição</a>

Para a remoção de um elemento na ultima posição do array, podemos utilizar o método pop(): 
```
numbers.pop()

```


[Voltar ao Índice](#indice)

---


## <a name="parte10">10 - Usando o método shift </a>

Para a remoção de um elemnto da primeira posição, podemos utilizar o método shift()
```
numbers.shift()

```

[Voltar ao Índice](#indice)

---


## <a name="parte11">11 - Acrescentando e removendo elementos de uma posição específica </a>

É comum também a remoção de um elemento de uma posição especifica, o que nos leva ao método splice().
O metodo funciona de forma simples e recebe dois argumentos:
* O primeiro argumento indica a partir de qual o indice que queremos iniciar a remoção. 
* O segndo argumento indica quantos elementos serão removidos. 
Veja:

```
numbers.splice(5, 3)

```
O código acima irá remover tres elementos a partir do indice 5. Isso significa que o numbers[5], numbers[6] e numbers[7] serão eliminados. 
[Voltar ao Índice](#indice)

---

## <a name="parte12">12 - Arrays bidimensionais e multidimensionais</a>

Imagine-se na situação onde é necessario a anotação da temperatura em 3 horários do dia durante 2 dias. Até aqui, já é possivel imaginar que isso pode ser realizado através de array, fazendo um array das temperatura para cada dia. Seria algo assim:

```
let tempDiaUm = [18, 25, 20];
let tempDiaDois = [19, 23, 21];

```
Isso está certo até um determinado ponto. Pois imagine também que no decorrer destes dois dias, decidam que essa coleta de dados deverá ocorrer durnate um ano. Aqui já tornaria a situaçao de administrar tantas variaves mais complicada. Por isso, entramos em arrays bidimensionais. Veja a reconstrução da situação anterior com arrays bidimensionas:

```
let tempDia =[];
tempDia[0] = [18, 25, 20]
tempDia[1] = [19, 23, 21];

```
Isso torna o acesso à estes dados mais fácil, bastando indicar os indices das matrizes.
```
tempDia[0][1] = 25;
```
[Voltar ao Índice](#indice)

---

## <a name="parte13">13 - Iterando pelos elementos de arrays bidimensionais</a>

A iteraçao de uma matriz bimencional vai ser a introdução para entender a multidimensional.
Imagina a matriz do tópico anterior e que seja necessario percorrer por todos os seus valores. Usaremos uma função generica que terá um laço for e passará por cada um das linha e colunas da matriz. Veja:

```
function printMatrix(myMatrix) {
    for(let i = 0; i < myMatrix.length; i++) {
        for(let j = 0; j < myMatrix[i].length; j++){
            console.log(myMatrix[i][j])
        }
    }
}

```
Perceba que foi usado uma for aninhado para percorrer todas as linhas e colunas. Sendo o i as linhas e j as colunas. Caso queira exibir todo o conteudo da matriz, podemos usar o código:

```
printMatrix(tempDia);
```

[Voltar ao Índice](#indice)

---

## <a name="parte14">14 - Arrays multidimensionais</a>

Neste ponto, o aninhamento de for pode ficar um pouco confuso. Entretanto, se os exemplos de matriz bidimensionais foram bem entendidos, o entendimento aqui ficará facilitado. 
Vamos criar uma matriz 3x3. Cada célula contem a soma de i (linha) + j (coluna) + z (profundidade.) Deste modo, será necessario inicializar cada array, nao importa o tamanho da matriz, precisamos percorrer cada dimensão a fim de acessar a celula

```
const matrix3x3x3 = [];
for(let i = 0; i < 3; i++) {
    matrix3x3x3[i] = [];
    
for(let j = 0; j < 3; j++){
     matrix3x3x3[j] = []

for(let z = 0; z < 3; z++){
    matrix3x3x3[i][j][z] = i + j + z; 
}
 }   
}

```

Para exibir o resultado da matriz, poderia escrever um laço for também utilizando o .length. 

```
for(let i = 0; i < matrix3x3x3.length; i++) {   
    for(let j = 0; j < matrix3x3x3[i].length; j++){
        for(let z = 0; z < matrix3x3x3[i][j].length; z++){
         console.log(matrix3x3x3[i][j][z])
}
 }   
}

```

[Voltar ao Índice](#indice)

---


## <a name="parte15">15 - Referências para métodos de array em JavaScript</a>

Os arrays em JS são objetos modificados, ou seja, todo array que criamos possui algum método disponivel para uso. Nos proximos tópicos são alguns métodos essenciais.

[Voltar ao Índice](#indice)

---


## <a name="parte16">16 - Juntando vários arrays</a>

Em um cenário onde se faz necessario a junção de alguns arrays é visto o uso do método concat. Como o nome sugere, ele faz a concatenção dos arrays. Veja:

```
const zero = 0; 
const positivos = [1, 2, 3];
const negativos = [-3, -2, -1]

let numbers = negativos.concat(zero, positivos)

```

[Voltar ao Índice](#indice)

---

## <a name="parte17">17 - Funções de iteração</a>

Para fim de entendimento dos próximos tópicos considere a função isEven()

```
function isEven(x) {
    console.log(x)
    return x % 2 === 0 ? true : false;
}

let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]

```
[Voltar ao Índice](#indice)

---

## <a name="parte18">18 - Iterando com o método every</a>

O método every irá passar por todos os elementos e verificar se é true ou false. Ele verifica até que a condicao retorne false, ai ele para.
```
numbers.every(isEven)
```
Como em nosso exemplo o primeiro número é 1, ele retorna false
[Voltar ao Índice](#indice)

---

## <a name="parte19">19 - Iterando com o método some</a>

Este método é o oposto do anterior, irá iterar os elementos até que retorne true

```
numbers.some(isEven)
```
[Voltar ao Índice](#indice)

---

## <a name="parte20">20 - Iterando com forEach</a>

Como o nome já indica, este método é parente proximo de um laço já visto aqui. O for. Portando, seu resultadno será semelhante ao do laço, irá iterar todos os elementos do array

[Voltar ao Índice](#indice)

---

## <a name="parte21">21 - Usando map e filter</a>

Bom, tantos map() quanto o filter() irão nos retornar um novo array com o resultado da iteração de cada um dos elemetnos. Entretando, o map() nos retorna o resultado de __todos os elementos__, enquanto o filter nos manda um array __com os elementos que deram true__

* map()
```
const myMap = numbers.map(isEven)
```
irá retornar: [false, true, false, true, false, true, false, true, false, true, false, true, false, true, false]

* filter()
```
const evenNumbers = numbers.filter(isEven)
```
irá retornar: [2, 4, 6, 8, 10, 12, 14]
[Voltar ao Índice](#indice)

---

## <a name="parte22">22 - Usando o método reduce</a>

Por fim, temos o método reduce. Reduce recebe 4 parametros: previousValue, currentValue, index e array. Os parametros index e array são opcionais, podemos passar apenas os dois primeiros. Este método será muito útil caso queria somar todos os elementos de um array. Veja o exemplo:

```
numbers.reduce((previous, current) => previous + current)

```
A saída deste comando será 120, que é a soma de todos os elementos de numbers

[Voltar ao Índice](#indice)

---
_Uma obs aqui, os últimos 3 métods vistos aqui(map, filter e reduce), serão de suma importancia quando for visto programação funcional_

## <a name="parte23">23 - ECMAScript 6 e novas funcionalidades de Array</a>

A seguir teremos exemplos de alguns novos métodos adicionados aos arrays com o ES6

[Voltar ao Índice](#indice)

---

## <a name="parte24">24 - Iterando com o laço for..of</a>

for...of é uma nova forma de iterar por um array, forma essa introduzida pelo ES6. Nao é tao diferente de um laço for padrao, veja o exemplo

```
for(const n of numbers){
    console.log(n % 2 === 0 ? 'even' : 'odd')
}
```

[Voltar ao Índice](#indice)

---


## <a name="parte25">25 - Ordenando elementos</a>

Neste tópico usaremos ao array numbers que já temos, para isso, iremos deixar seu elementos fora de ordem e depois colocar em ordem novamente...

```
numbers.reverse()
```
Aqui, temos todo o array invertido de forma decrescente: numbers = [15, 14, 13, 12, 11, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1]

```
numbers.sort()
```
Aqui ele já terá a seguinte saída: numbers= [1, 10, 11, 12, 13, 14, 15, 2, 3, 4, 5, 6, 7, 8, 9]

Agora podemos implementar uma função de comparação depois executar o sort() novamente. Antes, precisamos entender o seguinte. O código a seguir irá retornar um numero negativo se b for maior que a, um numero positivo se a for maior que b e zero se forem iguais. Para que consigamos colocar todo o array em ordem novamente, faremos uma funcao de comparação logo abaixo. Veja como irá acontecer:

```
numbers.sort((a, b)=> a - b)
```

```
function compare(a, b){
    if(a < b){
        return -1
    } 
    if (a > b ) {
        return 1
    }
    return 0;
}

numbers.sort(compare)
```

Dessa forma, todos os elementos do array estarão em ordem.
[Voltar ao Índice](#indice)

---

## <a name="parte26">26 - Convertendo um array em uma string</a>

Bom, se quisermos exibir todos os elementos do array no console em formato de string, podemos executar o método toString().

```
console.log(numbers.toString())
```

Agora se a ideia for exibir todos os elemento com uma sepação entre eles, usamos o método join()

```
const numbersString = numbers.join('-')
console.log(numbersString)
```

[Voltar ao Índice](#indice)

---


## <a name="parte27">27 - Classe TypedArray</a>



[Voltar ao Índice](#indice)

---


## <a name="parte27">27 - Resumo</a>

Neste cápitulo foi visto como declarar, inicializar, remover valores, atribiur valores. Conhecemos arrays bidimensionais, multidimensionais e também como os pruncipais métodos funcionam. 
Também conhecemos os novos métodos e funcionalidades do ECMAScript 2015 e 2016

[Voltar ao Índice](#indice)

---

__THE END__