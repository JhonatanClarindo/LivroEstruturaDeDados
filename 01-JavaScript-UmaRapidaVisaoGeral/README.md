# 1. JavaScript - uma rápida visão geral

## O primeiro capítulo da livro aborda um básico sobre a linguagem JavaScript. O que será necessário para o restante do livro. É visto também a configuração do ambiente para melhor entendimento sobre o conteúdo.

## <a name="indice">Índice</a>
Resumo do cap 01

---
1. [Estrutura de dados e algoritmos em JavaScript](#parte1)     
2. [Básico sobre o JavaScript](#parte2)     
3. [Variáveis](#parte3)     
4. [Operadores](#parte4)     
5. [Truthy e falsy](#parte5)     
6. [Funções dos operadores de igualdade (== e ===)](#parte6)     
7. [Estruturas de controle](#parte7)     
8. [Laços](#parte8)     
9. [Funções](#parte9)     
10. [Programação orientada a objetos em JavaScript](#parte10)     
11. [Depuração e ferramentas](#parte11)       
15. [Resumo.](#parte12)     
---


## <a name="parte1">1 - Estrutura de dados e algoritmos em JavaScript</a>

Por que usar JS nas estruturas de dados?
Além de ser bem popular, JavaScript é uma linguagem funcional o que torna o aprendizado e entendimento das estruturas algo mais fácil do que se fosse em linguagens padrões como C, Java ou Python.
Além do mais, talvez você precise sim fazer algumas implementações enquanto desenvolve o frontend.
A importancia de se conhecer bem as estruturas de dados no final é bem simples, tanto para o seu entendimento e racioncinio para a resoluçao de problemas como para o desempenho da sua própria aplicação.

[Voltar ao Índice](#indice)

---


## <a name="parte2">2 - Básico sobre o JavaScript</a>

Antes de mais nada é importante mostrar que existem duas formas de usar o JavaScript em uma pagina web.
A primeira forma seria com a declaração da tag script e dentro da mesma, teriamos o código JS. Veja:
```
<script>
alert('olá, mundo')
</script>
```
A segunda maneira de se usar, seria anexando um arquivo .js no documento HTML. Veja:
```
<scritp src='index.js'></script>
```
[Voltar ao Índice](#indice)

---


## <a name="parte3">3 - Variáveis</a>

As variáveis armazenam dados que podem ser alterados, atualizados ou recuperados sempre que necessário.
Os tipos disponiveis para estes dados são: number, string, boolean, function, object, undefined, null.
É importante ressaltar que JS não é uma linguagem fortemente tipada, então, diferente de outras linguagens como o Java, ao declarar uma variável, não é necessário declarar seu tipo. 
Caso se faça necessário o uso do tipo, usaremos o Typescript.

[Voltar ao Índice](#indice)

---


## <a name="parte4">4 - Operadores</a>

Em qualquer linguagem de programação existem operadores. Em JavaScript não seria diferente. 
JS conta com operadores aritméticos, lógicos, bitwise, de atribuição, de comparação, unários e outros.
Veja alguns exemplos que podem ser mencionados brevemente.

## Aritmético
Operador  | Descrição
--------- | ------
    +     | Adição
    -     | Subtração
    *     | Multiplicação
    /     | Divisão
    %     | Resto da divisão
    ++    | Incremento
    --    | Decremento

## Atribuição
Operador  | Descrição
--------- | ------
    =     | Atribuição
    +=    | Atribuição de soma
    -=    | Atribuição de subtração
    *=    | Atribuição de multiplicação
    /=    | Atribuição de divisão
    %=    | Atribuição de resto

## Operador de comparação

Operador  | Descrição
--------- | ------
    ==    | Igual a
    ===   | Igual a (exatamente igual)
    !=    | Diferente d
    >     | Maior que
    <     | Menor que 
    >=    | Maior igual a 
    <=    | Menor igual a

## Operador lógico

Operador  | Descrição
--------- | ------
    &&    | E
    ||    | Ou
    !     | Negação
  

Existem outros operadores também, inseri apenas aqueles mais comuns e mais usados nestes exemplos.

[Voltar ao Índice](#indice)

---


## <a name="parte5">5 - Truthy e falsy</a>
Em JS, o true e false tem uma complexidade própria. Enquanto o True e False em outras linguagem quer dizer que algo é verdadeiro ou falso, em JS uma string pode ser true. 

A tabela abaixo ajuda a entender melhor isso:
Operador  | Descrição
--------- | ------
undefined | false
null      | false
Number    | false para +0, -0 ou NaN, caso contrário é true
String    | false se for vazia, se for >= 1 é true
Object    | true


[Voltar ao Índice](#indice)

---


## <a name="parte6">6 - Funções dos operadores de igualdade (== e ===)</a>
Os operadores de igualdade == e === podem ser um pouco confusos pela semelhança, porém é bem simples de diferenciar.
O == é usado quadno os valores são iguais, porém, são de tipos diferente. Já === é usado com valores que são exatamente igual tanto em valor quanto em tipo. Veja abaixo como o == pode funcionar

Type x    | Type y         |   x == y  
--------- | ---------------|------------------
null      | undefined      | true
undefined | null           | true
number    | string         | x == toNumber(y)
string    | number         | toNumber(x) == y
boolen    | any            | toNumber(x) == y
any       | boolen         | x == toNumber(y)
string or | object         | x == toPrimitive(y)
number
object    | string or numb | toPrimitive(x) == y

Se x e y forem do mesmo tipo, entao usará o método === para a comparação. Qualquer outra combinação nao listada resultará em false.
Os métodos toNumber() e toPrimitive() avaliam os valores internos 

Importante lembrar que para o método toNumber() os seguintes valores são considerados:
* undefined é NaN
* null é +0

[Voltar ao Índice](#indice)

---


## <a name="parte7">7 - Estruturas de controle</a>
Em JS as estruturas de controle são semelhantes aos das linguagens C e Java. Instruções condicionais seguem a estrutura de if...else e switch. Já as instruções de repetição seguem como o while, do...while e for.


[Voltar ao Índice](#indice)

---


## <a name="parte8">8 - Laços</a>
### For
Os laços são usados com frequencia quando trabalhamos com arrays. 
O laço for é constituido de um contador de laços que em geral, recebe um valor numérico e em seguida a variável. Que é entao comparada com o outro valor. Por fim, o valor numérico é incrementado ou decrementado.
Segue um breve e classico exemplo de laço for:

```
for(var i = 0; i < 10; i++) {
    console.log(i)
}

```
### While
O bloco de código dentro do laço é executado apenas se a condição for verdadeira. Veja um simples exemplo;

```
var i = 0;
while(i < 10){
    console.log(i);
    i++
}

```
### do...while
Diferente dos outros código, aqui o do..while garante que o código seja executado pelo menos uma vez. Veja:

```
var i = 0;
do {
    console.log(i)
}while (i < 10)

```
Veja que aqui, diferente dos exemplos anteriores, a variavel é chamada e depos é verificada a condição. Particularidade do laço do...while.
[Voltar ao Índice](#indice)

---

## <a name="parte9">9 - Funções</a>

Funções são partes fundamentais de JS, dada que é uma linguagem funcional. 
Uma função pode ser traduzida como algo que será realizado em um dado momento específico do código. Por exemplo exibir uma mensagem ao clicar em um botão. Veja um exemplo:
````
function exemplo(text) {
    console.log(text)
}

exemplo('este é um teste') 

````
Veja que aqui foi declarada uma função com um argumento texto. Dentro a função foi colocada uma instrução para ser executada quando for chamada.
Logo a baixo, a funcao foi chamada e inserido o argumento. A saída será o argumento passado.
[Voltar ao Índice](#indice)

---


## <a name="parte10">10 - Programação orientada a objetos em JavaScript</a>
Em POO, um objeto é uma instância de classes. Uma classe define as caracteristicas do objeto. Objetos em Javascript são coleções bem simples de pares-valor.
Para declarar um objetos, temos as seguintes maneiras: 
````
var obj = new Object();

var obj = {}
````

[Voltar ao Índice](#indice)

---


## <a name="parte11">11 - Depuração e ferramentas</a>
Saber depurar nada mais é que causa-consequencia de aprender a programar.
Para isso, existem algumas ferramentas para auxiliar neste ponto.
* Google Developer Tools
* VsCode
* WebStorm
* Atom

[Voltar ao Índice](#indice)

---


## <a name="parte12">12 - Resumo.</a>

Neste capitulo é visto o básico de JS e o necessário para dar inicio ao desenvolvimento dos algoritmos

[Voltar ao Índice](#indice)

---

