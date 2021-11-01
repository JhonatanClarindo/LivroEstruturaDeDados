# 4. Filas 
## O capítulo 5 mostra como criar, adicionar e remover elementos de uma fila. Também traz alguns problemas que podem ser resolvidos com a estrutura de dados fila.

Resumo do Cap. 05

## <a name="indice">Índice</a>

---
1. [Estrutura de dados da fila](#parte1)     
2. [Criando a classe Queue](#parte2)     
3. [Inserção de elementos na fila](#parte3)
4. [Remoção de elementos da fila](#parte4)
5. [Dando uma espiada no elemento que está na frente da fila](#parte5)
6. [Verificando se a fila está vazia e qual o seu tamanha](#parte6)
7. [Limpando a fila](#parte7)     
---


## <a name="parte1">1 - Estrutura de dados da fila</a>

Antes de mais nada, precisamos imaginar como é uma fila de cinema... O primeiro cliente que chega, é o primeiro a ser atendido. Em seguida, o segundo que chegou e assim por diante. Dito isso, vamos a estrutura de dados da fila.
Como foi visto no capítulo anterioe de pilhas, elas trabalham seguindo um principio chamado de LIFO. Aqui, temos o FIFO. First in, first out. A adição de um novo elemento na fila é feita na tail. E a remoção na frente.

[Voltar ao Índice](#indice)

---

## <a name="parte2">2 - Criando a classe Queue</a>

Para fins didáticos, vamos começar com a declaração da nossa classe:

```
class Queue {
    constructor() {
        this.count = 0;
        this.lowerCount = 0;
        this.items = {}
    }
}

```
Pode ser notado logo de cara que a class Queue é bem semelhante com a class Stack. Apenas os principios de remoção e adição que sao diferentes.
A partir deste tópico, serão utilizados alguns método que ajudaram no estudo e entendimento do conteúdo

* enqueue()
* dequeue()
* peek()
* isEmpty()
* size()
[Voltar ao Índice](#indice)

---

## <a name="parte3">3 - Inserção de elementos na fila</a>

O primeiro método é o enqueue(). Um detalhe, só é possivel adicionar itens no final da fila

```
enqueue(element) {
    this.items[this.count] = element
    this.count++
}
```

[Voltar ao Índice](#indice)

---

## <a name="parte4">4 - Remoção de elementos da fila</a>

Diferente do capítulo anterior, nas filas, para a remoção utilizamo uma condição if. Como as filas utilizam o principio FIFO, o primeiro a ser removido, será o primeiro a ser adicionado.

```
dequeue() {
    if(this.isEmpty()) {
        return undefinded;
    }
    const result = this.items[items.lowerCount];
    delete this.items[this.lowerCount]
    this.lowerCount++
    return result
}

```

[Voltar ao Índice](#indice)

---

## <a name="parte5">5 - Dando uma espiada no elemento que está na frente da fila</a>
 
 Assim como nas pilhas, aqui é usado o peek(), portando nao precisamos entrar em muitos detalhes

[Voltar ao Índice](#indice)

---

## <a name="parte6">6 - Verificando se a fila está vazia e qual o seu tamanho</a>

Assim como nas pilhas, aqui usamos o método isEmpty()

[Voltar ao Índice](#indice)

---

## <a name="parte7">7 - Limpando a fila</a>

Assim como nas pilhas, aqui usamos o método clear()

[Voltar ao Índice](#indice)

---