# 6. Listas Ligadas
## Neste capitulo será explicado como são as estruturas de dados de listas ligadas a partir do zero. Além disso, será descrito como declaras, criar, adicionar e remover elementos.

Resumo do Cap. 06

## <a name="indice">Índice</a>

---
1. [Estrutura de dados da lista ligada](#parte1)     
2. [Adição de elementos em uma lista ligada](#parte2)     
3. [Inserção de elementos no final da lista ligada](#parte3)
4. [Remoção de elementos de uma posição específica da lista ligada](#parte4)
5. [Percorrendo a lista com um laço até alcançar a posição desejada](#parte5)
6. [Refatorando o método remove](#parte6)
7. [Limpando a fila](#parte7)     
---

## <a name="parte1">1 - Estrutura de dados da lista ligada</a>

 Os arrays (ou melhor, listas) são provavelmente a estrutura de dados mais comum usada para armazenar uma coleção de elementos. As listas NÃO armazenam os elementos posicionados de forma contígua na memória. 
 Em uma lista, se quisermos acessar um elemento no meio, será necessário partir do inicio (cabeça ou head) e iterar pela lista até encontrarmos o elemento desejado.

[Voltar ao Índice](#indice)

---

## <a name="parte2">2 - Adição de elementos em uma lista ligada</a>

### Inserindo um elemento no final da lista ligada:

Para adicionar um elemnto ao final da lista é necessario iterar por toda a lista, até encontrar o ultimo item. Para isso, é necessário uma variável que aponte para o current atual na lista. Sabemos que chegou ao final quando o current.next retornar undefined ou null. Depois disso é só ligar o ponteiro next do current ao nó do elemento que queremos adicionar na lista.
Veja um exemplo: 

```
push(element){
    const node = new Node(element)
    let current;
    if(this.head == null){
        this.head = node
    } else{
        current = this.head
        while(current.next != null){
            current = next.current
        }
        current.next = node;
    }
    this.count++
}

```
### Inserindo um elemento em qualquer posição: 
 
 Para isso, usa-se o método insert(). Ele possibilita inserir um element em qualquer posição.



[Voltar ao Índice](#indice)

---

## <a name="parte1">1 - Estrutura de dados da lista ligada</a>

 
[Voltar ao Índice](#indice)

---