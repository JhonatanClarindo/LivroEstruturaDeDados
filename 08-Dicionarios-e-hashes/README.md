# 8. Dicionários e Hashs

# No geral, o Capítulo cobre os fundamentos de dicionários e tabelas hash, incluindo sua implementação e aplicações práticas. O capítulo também inclui vários exemplos e exercícios para ajudar os leitores a praticar e solidificar sua compreensão dos conceitos abordados.

Resumo do Cap. 08


## <a name="indice">Índice</a>

1. [Introdução aos dicionários](#parte1)     
2. [Introdução à Hashing](#parte2)     
3. [Introdução à Tabelas de Hash](#parte3)

## <a name="parte1">1 - Introdução aos dicionários </a>
Um dicionário é uma estrutura de dados que armazena pares chave-valor. Em JavaScript, os dicionários podem ser implementados usando objetos ou arrays. Por exemplo, para armazenar a população de diferentes cidades, podemos criar um dicionário usando um objeto:

```

const population = {
  "New York City": 8399000,
  "Los Angeles": 3990456,
  "Chicago": 2705994,
  "Houston": 2320268
};

```

## <a name="parte2">2 - Introdução à Hashing </a>

Hashing é uma técnica usada para mapear uma chave para um índice em uma tabela de hash. O objetivo do hash é encontrar rapidamente o valor associado a uma determinada chave. As funções hashing mais comuns são o método de divisão e o método de multiplicação. Por exemplo, para fazer o hash de uma chave de string "hello" usando o método de divisão, podemos fazer:

```

const key = "hello";
const hash = key.length % 7; // result is 2

```

## <a name="parte3">3 - Introdução à Tabelas de Hash </a>

Uma tabela de hash é uma estrutura de dados que armazena pares chave-valor usando uma matriz. Cada chave é hash para um índice na matriz e o valor é armazenado nesse índice. Se duas ou mais chaves hash são usadas para o mesmo índice, ocorre uma colisão e uma técnica de resolução de colisão é usada para resolvê-la. As duas técnicas mais comuns são sondagem linear e encadeamento. Por exemplo, para armazenar a população de diferentes cidades em uma tabela hash, podemos fazer:

```

class HashTable {
  constructor() {
    this.table = new Array(137);
  }
  put(key, value) {
    const hash = this.hash(key);
    this.table[hash] = value;
  }
  get(key) {
    const hash = this.hash(key);
    return this.table[hash];
  }
  hash(key) {
    let total = 0;
    for (let i = 0; i < key.length; i++) {
      total += key.charCodeAt(i);
    }
    return total % this.table.length;
  }
}

const population = new HashTable();
population.put("New York City", 8399000);
population.put("Los Angeles", 3990456);
population.put("Chicago", 2705994);
population.put("Houston", 2320268);
console.log(population.get("Chicago")); // output: 2705994

```


As tabelas hash podem ser usadas para resolver uma variedade de problemas, como encontrar elementos duplicados em uma matriz e contar a frequência de palavras em um texto. Por exemplo, para encontrar o primeiro caractere não repetido em uma string usando uma tabela hash, podemos fazer:

```JS
function firstNonRepeatedCharacter(str) {
  const charCount = new HashTable();
  for (let i = 0; i < str.length; i++) {
    const char = str[i];
    if (charCount.get(char)) {
      charCount.put(char, charCount.get(char) + 1);
    } else {
      charCount.put(char, 1);
    }
  }
  for (let i = 0; i < str.length; i++) {
    const char = str[i];
    if (charCount.get(char) === 1) {
      return char;
    }
  }
  return null;
}

console.log(firstNonRepeatedCharacter("hello world")); // output: "h"

```

