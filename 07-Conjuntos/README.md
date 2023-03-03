# 7. Conjuntos

# O capítulo fornece uma introdução aos conjuntos e suas operações, incluindo união, interseção, diferença e subconjunto. Neste capítulo, o autor também explica como implementar conjuntos em JavaScript e fornece exemplos de como usar conjuntos em cenários do mundo real

Resumo do Cap. 07


## <a name="indice">Índice</a>

1. [Introdução aos conjuntos](#parte1)     
2. [Definindo operações](#parte2)     
3. [Operações de Conjunto: União, Interseção, Diferença e Subconjunto](#parte3)

## <a name="parte1">1 - Introdução aos conjuntos </a>
Um conjunto é uma coleção de valores exclusivos, o que significa que cada valor em um conjunto só pode aparecer uma vez. Os conjuntos podem ser úteis para resolver uma variedade de problemas, como remover elementos duplicados de uma matriz ou encontrar a interseção de várias matrizes.

Em JavaScript, um conjunto pode ser implementado usando o objeto interno Set. O Setobjeto permite armazenar qualquer tipo de valor, incluindo tipos primitivos como números e strings, bem como objetos.

Aqui está um exemplo de como criar um conjunto em JavaScript:

```
const set = new Set();
set.add(1);
set.add(2);
set.add(3);

//Isso cria um novo conjunto contendo os valores 1, 2 e 3.

```

## <a name="parte2">2 - Definindo operações </a>
Os conjuntos suportam uma variedade de operações que permitem manipular seu conteúdo. Algumas das operações de conjunto mais comuns incluem:

`add:` Adicione um novo valor ao conjunto. 

`delete:` remove um valor do conjunto.

`has:` Verifique se um valor está no conjunto.

`size:` Obtenha o número de valores no conjunto.

`clear:` Remova todos os valores do conjunto.

`values:` Obtenha um iterador que retorna os valores no conjunto.

Aqui está um exemplo de como usar algumas dessas operações:

```
const set = new Set();
set.add(1);
set.add(2);
set.add(3);

console.log(set.has(2)); // true
console.log(set.size);   // 3

set.delete(2);
console.log(set.has(2)); // false
console.log(set.size);   // 2

set.clear();
console.log(set.size);   // 0

```

## <a name="parte3">3 - Operações de Conjunto: União, Interseção, Diferença e Subconjunto </a>
Os conjuntos também suportam uma variedade de operações que permitem combinar ou comparar conjuntos. Aqui estão algumas operações de conjunto comuns:

`union`: combine dois conjuntos em um novo conjunto que contém todos os valores de ambos os conjuntos.

`intersection:` crie um novo conjunto que contenha apenas os valores que aparecem em ambos os conjuntos.

`difference:` crie um novo conjunto que contenha apenas os valores que aparecem em um conjunto, mas não no outro.

`subset:` Verifique se um conjunto é um subconjunto de outro conjunto (ou seja, se todos os valores do primeiro conjunto também aparecem no segundo conjunto).

Aqui está um exemplo de como usar essas operações:

```
const set1 = new Set([1, 2, 3]);
const set2 = new Set([2, 3, 4]);

// Union
const union = new Set([...set1, ...set2]);
console.log(union); // Set {1, 2, 3, 4}

// Intersection
const intersection = new Set([...set1].filter(x => set2.has(x)));
console.log(intersection); // Set {2, 3}

// Difference
const difference = new Set([...set1].filter(x => !set2.has(x)));
console.log(difference); // Set {1}

// Subset
console.log(set1.has(2));    // true
console.log(set1.has(4));    // false
console.log(set1.isSubsetOf(set2));  // false

```