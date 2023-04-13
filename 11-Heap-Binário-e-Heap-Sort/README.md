# 11. Heap Binário e heap sort

# Neste cápitulo é abordado heap binário é um tipo de árvore binária usada para implementar uma fila de prioridade. 

Resumo do Cap. 11


## <a name="indice">Índice</a>

1. [Introdução Binary Heap](#parte1)     
2. [Sort Heap](#parte2)     

## <a name="parte1">1 - Introdução Binary Heap </a>
Um heap binário é um tipo de árvore binária usada para implementar uma fila de prioridade. Uma fila de prioridade é uma estrutura de dados em que cada elemento tem uma prioridade associada a ele e o elemento com a prioridade mais alta é retirado da fila primeiro. Heaps binários são particularmente úteis para implementar filas de prioridade porque permitem inserção, remoção e acesso eficientes ao elemento de prioridade mais alta.

Um heap binário é uma árvore binária completa, o que significa que todos os níveis da árvore são completamente preenchidos, exceto possivelmente o último nível, que é preenchido da esquerda para a direita. Em um heap binário, cada nó tem um valor maior ou igual aos valores de seus nós filhos. Isso é conhecido como "propriedade de heap".

Os heaps binários podem ser implementados como arrays, onde o primeiro elemento do array representa o nó raiz do heap. O filho esquerdo de um nó no índice i está localizado no índice 2i + 1, e o filho direito está localizado no índice 2i + 2. O pai de um nó no índice i está localizado no índice floor((i - 1) / 2 ).

Aqui está um exemplo de como implementar um heap binário em JavaScript:
```
class BinaryHeap {
  constructor() {
    this.heap = [];
  }

  insert(value) {
    this.heap.push(value);
    this.bubbleUp(this.heap.length - 1);
  }

  bubbleUp(index) {
    while (index > 0) {
      const parentIndex = Math.floor((index - 1) / 2);
      if (this.heap[parentIndex] >= this.heap[index]) {
        break;
      }
      [this.heap[parentIndex], this.heap[index]] = [this.heap[index], this.heap[parentIndex]];
      index = parentIndex;
    }
  }

  extractMax() {
    const max = this.heap[0];
    const last = this.heap.pop();
    if (this.heap.length > 0) {
      this.heap[0] = last;
      this.bubbleDown(0);
    }
    return max;
  }

  bubbleDown(index) {
    while (true) {
      const leftChildIndex = 2 * index + 1;
      const rightChildIndex = 2 * index + 2;
      let maxIndex = index;
      if (leftChildIndex < this.heap.length && this.heap[leftChildIndex] > this.heap[maxIndex]) {
        maxIndex = leftChildIndex;
      }
      if (rightChildIndex < this.heap.length && this.heap[rightChildIndex] > this.heap[maxIndex]) {
        maxIndex = rightChildIndex;
      }
      if (maxIndex === index) {
        break;
      }
      [this.heap[index], this.heap[maxIndex]] = [this.heap[maxIndex], this.heap[index]];
      index = maxIndex;
    }
  }
}

```
> Neste exemplo, criamos uma BinaryHeapclasse que usa um array para representar o heap binário. O insertmétodo adiciona um novo valor ao heap e, em seguida, o eleva até sua posição correta no heap. O extractMaxmétodo remove e retorna o elemento de maior prioridade do heap e, em seguida, desce o novo nó raiz para sua posição correta no heap.


## <a name="parte2">2 - Heap Sort </a>
Heap sort é um algoritmo de classificação que funciona primeiro construindo um heap binário a partir do array a ser classificado e, em seguida, extraindo repetidamente o elemento máximo do heap e colocando-o no final do array classificado. Aqui está um exemplo de como implementar o heap sort em JavaScript:

```
function heapSort(array) {
  const binaryHeap = new BinaryHeap();
  for (let i = 0; i < array.length; i++) {
    binaryHeap.insert(array[i]);

```