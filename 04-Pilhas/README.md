# 4. Pilhas 
## O capítulo explica como funciona a estrutura de dados de pilha, mostrando como criar, adicionar e remover elementos dela. Também mostra como resolver alguns problemas de ciencia da computação utilizando pilha.

Resumo do Cap. 04

## <a name="indice">Índice</a>

1.  [Estrutura de dados pilha](#parte1)     
2.  [Criando uma pilha](#parte2)     
3.  [Empilhando elementos na pilha](#parte3)     
4.  [Desempilhando elementos da pilha](#parte4)     
5.  [Dando uma espiada no elemento que está no topo da pilha](#parte5)     
6.  [Verificando se a pilha está vazia](#parte6)     
7.  [Limpando e exibindo os elementos da pilha](#parte7)     
8.  [Usando a classe Stack](#parte8)     
9.  [EcmaScript 6 e a classe Stack](#parte9)     
10. [Declarando a classe Stack usando a sintaxe da ES6](#parte10)     
11. [Classes ES6 com WeakMap](#parte11)     
12. [Resolvendo problemas usando pilhas](#parte12)     
13. [Decimal para binário](#parte13)     
14. [Algoritmo conversor de base](#parte14)     
15. [Resumo](#parte15)     
---


## <a name="parte1">1 - Estrutura de dados pilha</a>

Uma pilha obdece o principio de LIFO. Last in, first out. Isso nos diz que o ultimo a entrar, é o primeiro a sair. O final de uma pilha, é o topo e o lado oposto é a base. 

[Voltar ao Índice](#indice)

---

## <a name="parte2">2 - Criando uma pilha </a>

Com fins didáticos, será criada nossa própria pilha. Será usado um array como estrutara de dados que armazenará os elementos.

```
class Stack {
    constructor() {
        this.items = []
    }
}

```
A partir deste tópico, será utilizado alguns métodos nesta stack, sao eles:

* push()
* pop()
* peek()
* isEmpty()
* clear()
* size()
[Voltar ao Índice](#indice)

---

## <a name="parte3">3 - Empilhando elementos na pilha</a>

Método push(). Para o empilhamento de novos items na nossa pilha, usamos o método push(). lembre-se que ele adiciona elementos apenas ao topo da pilha, ou seja, no final. Ele é representado assim.

```
push(element){
    this.items.push(element)
}
```

[Voltar ao Índice](#indice)

---

## <a name="parte4">4 - Desempilhando elementos da pilha</a>

O método anterior adiciona ao topo da pilha, certo? Sendo assim e respeitando o principio LIFO, este método remove do topo da pilha. É o método pop() que também vimos no capitulo anterior.

```
pop(){
 return this.items.pop(element)
}
```

[Voltar ao Índice](#indice)

---

## <a name="parte5">5 - Dando uma espiada no elemento que está no topo da pilha </a>

Agora vemos um método auxiliar. Este método retorna o elemento que esta no topo da pilha, o método peek(). Veja:
```
peek() {
    return this.items[this.items.length - 1];
}
```
_Explicando o código =>_
Estamos usando um array para armazenar os elementos. Imagine que o array possui __três__ itens. Logo, o tamanho dele (_ou o length_) é 3. Pensando que em computação, contamos a partir do 0, temos;

[0] | [1] | [2]
--- | --- | ---
 81 |  72 | 100

Logo, se temos o tamanho que é 3 e subtraimos 1, temos o ultimo elemento; 100.
[Voltar ao Índice](#indice)

---

## <a name="parte6">6 - Verificando se a pilha está vazia </a>

O próximo método é simples, apenas verifica se a pilha está vazia e retorna true or false para isso. É o método isEmpty()
```
isEmpty() {
    return this.items.length == 0;
}
```
Um outro método que cabe neste tópico é o size(). Bem semelhante ao length, podemos ver qual o tamanho do array. Basta que retornemos o legth:

```
size() {
    return this.items.length
}
```
[Voltar ao Índice](#indice)

---

## <a name="parte7">7 - Limpando e exibindo os elementos da pilha</a>

De forma simples e direta. O método apenas limpa e esvazia a pilha.

```
clear(){
    this.items = []
}
```

[Voltar ao Índice](#indice)

---


## <a name="parte8">8 - Usando a classe Stack</a>

Neste tópico o autor insere uma sequencia de exemplos em como adicionar elementos à stack. O resumo e explicação, acredito que seria redundante pois são metódos já vistos anteriormente e até aqui, já é necessario ter-se a noção do que ocorre com a stack apenas pelos comandos feitos. Aqui, irei apenas instanciar a stack e deixar os códigos que o autor fez.

```
const stack = new Stack()
console.log(stack.isEmpty())

stack.push(5);
stack.push(8);

console.log(stack.peek()) 

stack.push(11);

console.log(stack.size())
console.log(stack.isEmpty())

stack.push(15)

stack.pop()
stack.pop()

console.log(stack.size())
```

[Voltar ao Índice](#indice)

---

## <a name="parte9">9 - EcmaScript 6 e a classe Stack</a>

Ao criar uma estrutura de dados ou um objeto que outros desenvolvedores podem usar tambem, devemos proteger os elementos internos para que somente os métodos que expusermos sejam usados para modificar a estrutura interna. 
Nessa caso, queremos usar a classe stack para ter acesso somente ao metodo que estamos expondo na classe. Vamos analisar algumas abordagem que o ES6 dispoem para isso.

[Voltar ao Índice](#indice)

---


## <a name="parte10">10 - Declarando a classe Stack usando a sintaxe da ES6</a>

Algun devs usam uma convenção com o underscore(_) para marcar uma classe como private. Esta não é apenas uma convencao como também protege os dados e dependendo do caso, do dev também

```
class Stack {
    constructot() {
        this._count = 0;
        this._items = {}
    }
}

```

[Voltar ao Índice](#indice)

---



## <a name="parte11">11 - Classes ES6 com WeakMap</a>

Esta é uma forma também de manter uma classe privada. O daod WeakMap armazena pares de chave/valor no qual a chave é um objeto e o valor pode ser um dado de qualquer tipo. Veja a aparencia:

```
const items = new WeakMap();
class Stack {
    constructor() {
        item.set(this, [])
    }
    push(element) {
        const s = items.get(this)
        s.push(element)
    }
    pop(){
        const s = items.get(this)
        const r = s.pop()
        return r
    }
}

```
Veja que neste bloco, foi declarado uma variavel como WeakMap. Em seguida definismos um constructor especificando this (_uma refencia à classe_) como chave do WeakMap. Logo depois, acessamos o valor de WeakMap passando this como chave.

Esta sim é uma boa propriedade privada. Dessa forma, nao fica tao fácil ler e nao é possivel herdar também as props private.
[Voltar ao Índice](#indice)

---

## <a name="parte12">12 - Resolvendo problemas usando pilhas</a>

Agora que foi visto como uma stack funciona, será usado alguns problemad de ciência da computação para finalizar. 

[Voltar ao Índice](#indice)

---


## <a name="parte13">13 - Decimal para binário</a>

Certo. Aqui, via de regra, é sabido por todos que um computador se comunica em numeros binário. Logo, para converter um decimal em binário, pode-se dividir o número por 2 até que o resultado dê 0.

Imagine o número 10. Agora ele será convertido para binário. Veja:
10/2 == 5 resto 0
5/2 == 2 resto 1
2/2 == 1 resto 0
1/2 == 0 resto 1
Para saber, pegamos os restos de baixo pra cima. Então o número 10 em binário seria 1010

Em algoritmo, veja como ficaria:
```
function decimalToBinary(decNumber) {
    const remStack = new Stack();
        let number = decNumber;
        let rem
        let binaryString = '';

    while(number > 0) {
        rem = Math.floor(number % 2)
        remStack.push(rem)
        number = Math.floor(number / 2)
    }    
    while(!remStack.isEmpty() {
        binaryString += remStack.pop().toString()
    }
    return binaryString
}
```

[Voltar ao Índice](#indice)

---


## <a name="parte14">14 - Algoritmo conversor de base </a>

Podemos usar também modificar o código acima para que ele funcione como um conversor de base de 2 a 36. Em vez de dividir por 2, passamos a base desejada como argumento. Veja:
```
function baseConverter(decNumber, base) {
    const remStack = new Stack()
    const digits = '0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ'
    let number = decNumber;
    let rem;
    let baseString = '';
    if(!(base >= 2 && base <= 36)) {
        return '';
    }
    while(number > 0) {
        rem = Math.floor(number % base) 
        remStack.push(rem)
        number = Math.floor(number / base)
    }
    while (!remStack.isEmpty()) {
        baseString += digits[remStack.pop()]
    }
    return baseString
}

```

[Voltar ao Índice](#indice)

---


## <a name="parte15">15 - Resumo</a>

Neste cápitulo, conhecemos a estrutura de dados de pilha. Implementamos o nosso próprio algoritmo para representar uma pilha usando arrays e um objeto JS e vimos como adicionar, remover elementos dela usando os métodos pop e push.

[Voltar ao Índice](#indice)

---

__THE FINISHED__