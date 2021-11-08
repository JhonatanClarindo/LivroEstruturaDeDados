# 7. Conjuntos
## Neste capitulo é apresentado a estrutura de dados de conjuntos e como ela pode ser usada para armazenar elementos nao repetidos

Resumo do Cap. 07

## <a name="indice">Índice</a>

---
1. [Estrutura de dados dos conjuntos](#parte1)     
2. [Criando uma classe Set do zero](#parte2)     
3. [Inserção de elementos](#parte3)
4. [Remoção de elementos](#parte4)
5. [Operações em conjunto](#parte5)
---


## <a name="parte1">1 - Estrutura de dados dos conjuntos</a>

 

[Voltar ao Índice](#indice)

## <a name="parte2">2 - Criando uma classe Set do zero</a>

Para entender melhor, neste exemplo estamos usando um objeto para representar o nosso conjunto (items), mas poderia ser usado também um Array.

```
class Set {
    constructor() {
        this.items = {}
    }
}
```

Antes de iniciar e começar a inserir ou deletar algum tipo de dado, é preciso implementar o primeiro método, que será responsavel por verificar se o elemento está ou nao no conjunto

```
has(element) {
    return element in items
}
```
 **OBS:** Como está sendo usado JS, podemos usar o método dessa forma, porém existe uma maneira mais correta de implementoar este método.

```
has(element) {
    return Object.prototype.hasOwnProperty.call(this.items, element)
}
``` 

 
[Voltar ao Índice](#indice)


## <a name="parte3">3 - Inserção de elementos</a>

Dados um certo element, podemos verificar se ele está presente no conjunto. Se não estiver, adicionamos

```
add(element) {
if(!this.has(element)) {
    this.items[element] = element;
    return true;
}
return false;
}
```
 
[Voltar ao Índice](#indice)

## <a name="parte4">4 - Remoção dos elementos</a>

Semelhante ao metódo anterior, no delete verificamos se o element está no conjunto. Se estiver, returna true e será removido, caso contrário, retorna false

```
delete(element){
    if(this.has(element)) {
        delete this.items[element]
        return true
    }
    return false
}


```

[Voltar ao Índice](#indice)


## <a name="parte5">5 - Operações em conjuntos</a>
O conjunto é um dos conceitos mais básicos da matemática e é muito importante na computação. 
Quando falamos de banco de dados, indiretamente estamos falando de conjuntos. Quando criamos uma consulta para obter um conjunto de dados em um banco, estamos usando notação de conjunto.
Em um banco de dados SQL, por exemplo, podemos obter dados que são comuns a duas tabelas, ou em apenas uma. Essas operações sao conhecidads como join e a base das joins em SQL sao operações em conjunto.
 
Sendo assim, podemos realizar as operações: 
* União
* Intersecção
* Diferença 
* Subconjunto
[Voltar ao Índice](#indice)