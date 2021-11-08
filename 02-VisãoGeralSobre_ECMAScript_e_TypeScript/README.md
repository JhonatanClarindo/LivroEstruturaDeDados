# 2. Visão Geral sobre ECMAScript e TypeScript

## O capítulo 2 irá tratar de algumas funcionalidades do JS introduzidas com o ES5 e também inclui algumas funionalidades do TypeScript. Um subconjunto de JavaScript

## <a name="indice">Índice</a>
Resumo do Cap. 02

---
01. [Introdução à ECMAScript](#parte01)     
02. [Usando Babel.js](#parte02)     
03. [Funcionalidades da ECMAScript 2015+](#parte03)     
04. [Templates Literais](#parte04)     
05. [Arrow Function](#parte05)     
06. [Operador ...rest](#parte06)     
07. [POO com Classes](#parte07)     
08. [Herança](#parte08)     
09. [Getters e Setters](#parte09)     
10. [Módulos](#parte10)     
11. [Introdução ao TypeScript](#parte11)          
12. [Inferencia de tipo](#parte12)
13. [Interfaces](#parte13)
14. [Resumo.](#parte14)     
---


## <a name="parte01">01 - Introdução à ECMAScript</a>

A linguagem JavaScritp evolui muito ano após ano. Desde 2015 tem havido uma nova versão lançada a cada ano, que é chama de ECMAScript. 
Um recurso que realmente vem ajudando muito no desenvolvimento utilizado JS e que foi incluída em uma das versões lançadas foi o TypeScript, um subconjunto de JS.


[Voltar ao Índice](#indice)

---

## <a name="parte02">02 - Usando Babel.js</a>

O Babel.js é um transpilador JavaScript, também chamado de compilador. Ele converte código JS com recursos da linguagem ECMAScript para um código equivalente.

[Voltar ao Índice](#indice)

---

## <a name="parte03">03 - Funcionalidades da ECMAScript 2015+</a>

A partir deste ponto, veremos funcionalidades da ES2015 que poderão e serão muito útil na programação JS, principalmente se conciliada com TS.

[Voltar ao Índice](#indice)

---

## <a name="parte04">04 - Templates Literais</a>
Os templates literais é um recurso que irá ser de grande ajuda na concatenação de strings. Para simplificar o entendimento, veja este exemplo (rimou)

````
console.log(`U are reading ${book.name}.,
            and this is a line
            and so is this`)

````
Veja que não houve a necessidade de usar aquela concatenação em que era colocada a string o sinal de + e o restante da string e assim por diante. Note também que nao existe masi necessidade de usar \n para a quebra de linha, basta apertar o enter. 

[Voltar ao Índice](#indice)

---

## <a name="parte05">05 - Arrow Function</a>

As funções seta ou arrow function, são também uma forma de facilitar a sintaxe de uma função na qual a maior diferença esta na omissão da palavra reservada function e utilizaão da seta =>. Veja:
Este é um exemplo de uma função antes da ES2015
````
var area = function circleArea(r){
    var PI = 3.14;
    var area = PI * r * r;
    return area;
}

````
Este seria uma function comum no anterior ao ECMA, agora veja como pode ser escrita a mesma função utilizando a função sera:

````
const area = r => {
    const PI = 3.14;
    const area = PI * r * r;
    return area;
}

````

[Voltar ao Índice](#indice)

---

## <a name="parte06">06 - Operador ...rest</a>

Aqui chegamos em um ponto muito interessante pois tocaremos em um ponto que ao trabalhar com arrays futuramente será de grande ajuda. 
Na ES5, podemos transformar arrays em parametros. Para ficar claro, veja no exemplo:

````
function sum(x, y, z) {
    return x + y + z;
}

let params = [3, 4, 5]
console.log(sum(...params)) 

````

[Voltar ao Índice](#indice)

---

## <a name="parte07">07 - POO com Classes</a>
O ECMA também trouxe uma maneira mais limpa de declarar classes. 
_Veja uma maneira de declarar uma classe sem o ECMA_

````
function Book(title, pages, isbn) {
    this.title = title;
    this.pages = pages;
    this.isbn = isbn;
}
Book.prototype.printTitle = function() {
    console.log(this.title)
}
````

_Agora note como melhoramos a sintaxe com o ECMA_

````
class Book {
    constructor(title, pages, isbn) {
        this.title = title;
        this.pages = pages;
        this.isbn = isbn;
    }
printIsbn() {
    console.log(this.isbn)
}
}

````


[Voltar ao Índice](#indice)

---

## <a name="parte08">08 - Herança</a>

Podemos extender uma classe e herdar seu comportamento usando a palavra reservada __extends__. No constructor também podemos referenciar o contructor da super classe usando a palavra reservada __super__. 
__É importante resaltar que por mais que essa declaração de classe seja semelhante à Java e C/C++, POO em JS é realizada através de protótipos__

````
class ITBooks extends Book {
    constructor(title, pages, isbn, technology) {
        super(title, pages, isbn);
        this.technology = technology
    }
printTechnology() {
    console.log(this.technology)
}
}

let jsBook = new ITBook('Learning JS Algorithms', '200', '12345678', 'JavaScript');
console.log(jsBook.title)
console.log(jsBook.printTechnology())
````


[Voltar ao Índice](#indice)

---

## <a name="parte09">09 - Getters e Setters</a>

Com o ECMA também veio o conceito de get e set

````
class Person {
    constructor(name) {
        this._name = name
    }

    get name() {
        return this._name;
    }

    set name(value) {
        this._name = name
    }
}

let lotChar = new Person('Frodo')

````

[Voltar ao Índice](#indice)

---

## <a name="parte10">10 - Módulos</a>
Em resumo, a ES2015 introduziu uma funcionalidade oficial de módulo no JS.
São eles:

* import
* export

[Voltar ao Índice](#indice)

---

## <a name="parte11">11 - Introdução ao TypeScript</a>

O TypeScript é um subconjunto do JS gradualmente tipado. Foi criado para permitir os devs potencializar o JavaScript. Entre seus recursos, está a possibilidade de usar tipagem em variáveis. Os tipos JS permitem verificação estática, facilitando refatorar o código e ecnotrar bugs.

[Voltar ao Índice](#indice)

---

## <a name="parte12">12 - Inferencia de tipo</a>

O TypeScript tem inferencia de tipo, o que significa que ele verifica e aplica um tipo a uma variável de forma automatica. Entretando, se houver a necessidade de inicializar uma variável sem valor, recomenda-se que seja tipada. Dessa forma

````
let favoriteLanguage: string;
let langs = ['JavaScript', 'Ruby', 'Pyhton'];
favoriteLanguage = langs[0]

````


[Voltar ao Índice](#indice)

---

## <a name="parte13">13 - Interfaces</a>

O primeiro conceito de interfaces é uma descrição de atributos e metódos que um objeto deve ter. Isso também permite que o VSCode tenho o preenchimento automático. 
Veja como pode ser feito:

````
interface Person {
    name: string;
    age: numer;
}

function printName(person: Person){
    console.log(person.name)
}


const john = {name: 'John', age: 25}
const mary = {name: 'Mary', age: 21, phone: '91234-4321'}

````
O código acima não possui nenhm tipo de erro de compilação. Mesmo que a segunda variavel fuga do padrao declarado. Isso ocorre por um conceito que existe em TypeScript chamado duck typing. Se algo nada como um pato, se parece com um pato, faz quack como um pato, então é um pato...
Ou seja, a variavel mary se comporta como a interface Person, logo, deve ser uma Person. 

[Voltar ao Índice](#indice)

---

## <a name="parte14">14 - Resumo.</a>

Neste capitulo foi visto as funcionalidade do ES2015+ que ajudarao a simplificar a sintaxe do TS.

[Voltar ao Índice](#indice)

---

