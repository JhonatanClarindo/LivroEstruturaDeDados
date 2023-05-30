# 14. Designs de Algoritmos e técnicas

# Neste capítulo será tratado sobre algumas técnicas para solucionar problemas envolvendo algoritmos.

Resumo do Cap. 14


## <a name="indice">Índice</a>

1. [Dividir para consquistar](#parte1)     
2. [Algoritmo de Busca binária](#parte2)
3. [Programação funcional vs Programação imperativa](#parte3)  

## <a name="parte1">1 - Dividir para conquistar </a>
Tática que ficou muito conhecida com o imperador romano Júlio César durante suas conquistas territóriais, garante a vitória sobre um determinado grupo a partir da sua fragmentação.

Em programação, o conceito também é uma abordagem para o design de algoritmos. O problema é divido em subproblemas, semelhante ao problema original; os subproblemas são resolvidos recursivamente e as soluções dos mesmos são combinadas ao fim.

A ideia é dividir o algoritmo em três partes:

**DIVIDIR** o problema em problemas mmenores.

**CONQUISTAR** os subproblemas menores resolvendo-os com algoritmos de recursividade.

**COMBINAR** as soluções dos subproblemas na soluçãop do problema original.


## <a name="parte2">2 - Algoritmo de busca binária </a>
Usando o conceito de *Dividir e conquistar*, implementaremos um algoritmo de busca binária. A lógica será:

**DIVIDIR:** calcular o mid e procurar o valor na metade inferior ou metade superior do array

**CONQUISTAR:** procurador o valor na metade inferior ou superior.

**COMBINAR:** não é aplicavél, pois estamos devolvendo os índices diretamente.

```
function binarySearch(arr, target) {
  let low = 0;
  let high = arr.length - 1;

  while (low <= high) {
    let mid = Math.floor((low + high) / 2);

    if (arr[mid] === target) {
      return mid;
    } else if (arr[mid] < target) {
      low = mid + 1;
    } else {
      high = mid - 1;
    }
  }

  return -1;
}
```

Neste algoritmo, o **arr** seria uma matriz ordenada no qual queremos encontrar o **target** que pode ser um valor dentro desta matriz. As variáveis **low** e **high** acompanham os limites do array. Inicialmente, **low** é definido como o primeiro indice e **high** é definido como o último índice (**arr.length - 1**).

O algoritmo divide iterativamente o espaço de busca pela metade calculando o índice do meio, **mid**, usando **Math.floor((low + high) / 2)**. Em seguida, ele compara o valor em **arr[mid]** com o alvo. Se forem iguais, o alvo foi encontrado e o algoritmo retorna o índice **mid**. Se **arr[mid]** for menor que o alvo, o algoritmo é atualizado para **low** recebe **mid + 1** e pesquisa a metade direita da matriz. Se **arr[mid]** for maior que o alvo, o algoritmo atualiza **high** para **mid - 1** pesquisar a metade esquerda da matriz.

O algoritmo continua dividindo o espaço de busca pela metade até que o alvo seja encontrado ou até que o lowíndice se torne maior que o highíndice. Se o destino não for encontrado, o algoritmo retornará -1 para indicar que o elemento de destino não está presente na matriz.


## <a name="parte3">3 - Programação funcional vs Programação imperativa </a>
Até aqui, foram feitos algoritmos utilizando o paradigma de programação imperativa. Onde programamos passo a passo em detalhes o que deve ser feito e em que ordem deve ocorrer. 

Neste atual ponto, será introduzido o paradigma de programação funcional. Este é utilizado em ambientes acadêmicos e graças à linguagens como Python e Ruby, começou a ser introduzida no mercado. 

Deselvover utilizando o paradigma de programação funcional é um questão de se acostumar com o modo como o paradigma funciona.
Veja a comparação entre estas duas implesmentação, cada uma utilizando um paradigma.

```
//funcao imperativa

function sumImperative(arr) {
  let sum = 0;

  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }

  return sum;
}
```

```
//funcao funcional

function sumFunctional(arr) {
  return arr.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
}
```

Na programação funcional, deve-se evitar efeitos colaterais e dados mutáveis. Isso significa que nao modificaremos os dados passados para a função. Se houver a necessidade de devolver uma solução com base na entrada, podemos criar uma cópia e devolver a mesma com os dados modificados.