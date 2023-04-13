# 10. Árvores

# Neste cápitulo é abordado árvores, suas propriedades e as diversas formas de percorrer por uma estrutura de dados de árvores.

Resumo do Cap. 10


## <a name="indice">Índice</a>

1. [Terminologia de árvores](#parte1)     
2. [Árvores binárias e árvores binárias de busca](#parte2)     
3. [Árvore AVL](#parte3)

## <a name="parte1">1 - Terminologia de árvores </a>

Uma árvore é uma estrutura de dados hierárquica que consiste em nós conectados por arestas. Cada nó em uma árvore possui um nó pai (exceto o nó raiz) e zero ou mais nós filhos. O nó raiz é o nó de nível superior na árvore e os nós folha são nós sem filhos. As árvores são usadas para representar relacionamentos hierárquicos, como sistemas de arquivos, organogramas e árvores genealógicas.

O capítulo explica as diferentes maneiras de percorrer uma estrutura de dados em árvore, como a travessia em profundidade e a travessia em largura. A travessia em profundidade começa no nó raiz e explora o máximo possível ao longo de cada ramificação antes de retroceder. Existem três tipos de travessia em profundidade: travessia em pré-ordem, travessia em ordem e travessia em pós-ordem. A travessia em largura, por outro lado, visita todos os nós no mesmo nível antes de passar para o próximo nível.

Aqui está um exemplo de uma árvore binária e sua travessia em JavaScript:

```
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

// Create a binary tree
const root = new TreeNode(1);
root.left = new TreeNode(2);
root.right = new TreeNode(3);
root.left.left = new TreeNode(4);
root.left.right = new TreeNode(5);

// Perform depth-first traversal (pre-order)
function preOrderTraversal(node) {
  if (node) {
    console.log(node.value);
    preOrderTraversal(node.left);
    preOrderTraversal(node.right);
  }
}

preOrderTraversal(root); // Output: 1 2 4 5 3

```

Neste exemplo, criamos uma árvore binária e realizamos uma travessia de pré-ordem para visitar cada nó na árvore na ordem raiz-esquerda-direita. A saída do percurso é 1 2 4 5 3.

O capítulo também aborda algoritmos de travessia de árvore e sua implementação em JavaScript. Por exemplo, o algoritmo de busca em largura pode ser usado para encontrar o caminho mais curto entre dois nós em uma árvore. Aqui está um exemplo de busca em largura em JavaScript:

```
// Perform breadth-first search
function breadthFirstSearch(node, target) {
  const queue = [node];
  
  while (queue.length) {
    const currentNode = queue.shift();
    
    if (currentNode.value === target) {
      return true;
    }
    
    if (currentNode.left) {
      queue.push(currentNode.left);
    }
    
    if (currentNode.right) {
      queue.push(currentNode.right);
    }
  }
  
  return false;
}

console.log(breadthFirstSearch(root, 5)); // Output: true

```


## <a name="parte2">2 - Árvores binárias e árvores binárias de busca </a>

Uma árvore binária é uma estrutura de dados em árvore na qual cada nó tem no máximo dois filhos, conhecidos como filho esquerdo e filho direito. As árvores binárias são usadas para representar relacionamentos hierárquicos e podem ser usadas para vários aplicativos, como pesquisa, classificação e compactação de dados.

Uma árvore de pesquisa binária (BST - Binary Search Tree) é um tipo de árvore binária que satisfaz as seguintes propriedades:

- A subárvore esquerda de um nó contém apenas nós com valores menores que o valor do nó.
- A subárvore direita de um nó contém apenas nós com valores maiores que o valor do nó.
- As subárvores esquerda e direita também são BSTs.

O livro explica os algoritmos usados ​​para percorrer, pesquisar, inserir e excluir nós em uma árvore de pesquisa binária. Esses algoritmos são baseados nas propriedades do BST e aproveitam o fato de que a árvore é classificada.

Eis um exemplo de uma árvore de pesquisa binária e suas operações de passagem, pesquisa, inserção e exclusão em JavaScript:

```
class Node {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinarySearchTree {
  constructor() {
    this.root = null;
  }
  
  // Insert a new node with the given value
  insert(value) {
    const node = new Node(value);
    
    if (!this.root) {
      this.root = node;
      return this;
    }
    
    let current = this.root;
    
    while (true) {
      if (value === current.value) {
        return undefined;
      }
      
      if (value < current.value) {
        if (!current.left) {
          current.left = node;
          return this;
        }
        current = current.left;
      } else {
        if (!current.right) {
          current.right = node;
          return this;
        }
        current = current.right;
      }
    }
  }
  
  // Search for a node with the given value
  search(value) {
    let current = this.root;
    
    while (current) {
      if (value === current.value) {
        return current;
      }
      
      if (value < current.value) {
        current = current.left;
      } else {
        current = current.right;
      }
    }
    
    return null;
  }
  
  // Traverse the tree in-order
  inOrderTraversal(node = this.root) {
    if (!node) {
      return [];
    }
    
    const left = this.inOrderTraversal(node.left);
    const right = this.inOrderTraversal(node.right);
    
    return [...left, node.value, ...right];
  }
  
  // Delete a node with the given value
  delete(value) {
    const deleteNode = (node, value) => {
      if (!node) {
        return null;
      }
      
      if (value === node.value) {
        if (!node.left && !node.right) {
          return null;
        }
        
        if (!node.left) {
          return node.right;
        }
        
        if (!node.right) {
          return node.left;
        }
        
        let temp = node.right;
        
        while (temp.left) {
          temp = temp.left;
        }
        
        node.value = temp.value;
        node.right = deleteNode(node.right, temp.value);
        
        return node;
      }
      
      if (value < node.value) {
        node.left = deleteNode(node.left, value);
        return node;
      }
      
      node.right = deleteNode(node.right, value);
      return node;
    }
    
    this.root = deleteNode(this.root

```



## <a name="parte3">3 - Árvore AVL  </a>
Claro, eu ficaria feliz em explicar as árvores AVL com mais detalhes!

As árvores AVL são um tipo de árvore de busca binária autobalanceada. Uma árvore de pesquisa binária é uma estrutura de dados onde cada nó tem no máximo dois nós filhos, e o nó filho esquerdo contém um valor menor que o nó pai, enquanto o nó filho direito contém um valor maior que o nó pai.

Um dos desafios do uso de árvores binárias de busca é que a árvore pode ficar desbalanceada com o tempo. Isso pode acontecer se uma série de valores for inserida na árvore em ordem crescente ou decrescente, o que pode levar a uma árvore distorcida que é ineficiente para pesquisar, inserir ou excluir valores.

As árvores AVL resolvem esse problema mantendo uma propriedade de equilíbrio que garante que as alturas das subárvores esquerda e direita de qualquer nó difiram no máximo um. Em outras palavras, uma árvore AVL é "balanceada em altura". Essa propriedade de equilíbrio é alcançada por meio de um processo chamado "rotação", que envolve alterar a estrutura da árvore movendo os nós.

Aqui está um exemplo de como a rotação funciona em uma árvore AVL:

_Digamos que temos a seguinte árvore de pesquisa binária:_
```
     10
    /  \
   5    15
  / \
 2   7

```

Nesta árvore, a subárvore esquerda tem altura 2, enquanto a subárvore direita tem altura 1. Isso significa que a árvore não está balanceada de acordo com a propriedade AVL. Para balancear a árvore, podemos realizar uma "rotação à direita" na subárvore com raiz no nó 5. Isso envolve promover o nó 5 à raiz da subárvore, com o nó 2 como filho esquerdo e o nó 7 como filho direito. O nó 10 se torna o filho certo do novo nó raiz e o nó 15 permanece como o filho certo do nó 10.


_A árvore AVL resultante ficaria assim:_
```
    7
   / \
  5   10
 /   / \
2   15  25

```

Agora a árvore está balanceada em altura, com ambas as subárvores tendo uma altura de 2.

As árvores AVL são eficientes para pesquisar, inserir e excluir valores, com uma complexidade de tempo de pior caso de O(log n), onde n é o número de nós na árvore. No entanto, manter a propriedade balance requer sobrecarga adicional, portanto, o desempenho real pode depender do caso de uso específico.