# 12. Gráfos

# Neste cápitulo é abordado os gráfos e suas propriedades.

Resumo do Cap. 12


## <a name="indice">Índice</a>

1. [O que são os gráfos](#parte1)     
2. [Representação](#parte2)     
3. [Busca em Profundidade e Busca em Largura](#parte3)

## <a name="parte1">1 - O que são os gráfos </a>

Existem diferentes tipos de gráficos, como gráficos direcionados e não direcionados, gráficos ponderados e não ponderados e gráficos cíclicos e acíclicos. Um gráfico direcionado tem arestas com uma direção, o que significa que você só pode viajar de um vértice para outro na direção da aresta. Um gráfico não direcionado tem arestas sem direção, o que significa que você pode viajar entre os vértices em qualquer direção. Um gráfico ponderado atribui um peso numérico a cada aresta, enquanto um gráfico não ponderado não. Um grafo cíclico tem pelo menos um ciclo (um caminho que começa e termina no mesmo vértice), enquanto um grafo acíclico não tem nenhum ciclo.

## <a name="parte2">2 - Representação </a>

Existem diferentes maneiras de representar grafos, como usar matrizes de adjacência ou listas de adjacência. Uma matriz de adjacência é uma matriz 2D onde as linhas e colunas representam vértices e os valores representam a presença ou ausência de uma aresta entre os vértices. Uma lista de adjacência é uma coleção de listas, onde cada lista representa os vértices adjacentes a um determinado vértice.


## <a name="parte3">3 - Busca em Profundidade e Busca em Largura </a>

O DFS começa em um vértice específico e explora o máximo possível ao longo de cada ramificação antes de retroceder. O BFS começa em um determinado vértice e explora todos os vértices vizinhos antes de passar para o próximo nível de vértices. Esses algoritmos podem ser usados ​​para resolver vários problemas relacionados a grafos, como encontrar o caminho mais curto entre dois vértices.

Por exemplo, digamos que você tenha um grafo de rede social onde os vértices representam pessoas e as arestas representam amizades. Você pode usar o BFS para encontrar todas as pessoas conectadas a uma determinada pessoa e o DFS para encontrar o caminho mais curto entre duas pessoas.