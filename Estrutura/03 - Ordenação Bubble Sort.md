# Algoritmos de Ordenação

## O que são algoritmos de ordenação?

Quando trabalhamos com uma grande quantidade de dados, muitas vezes precisamos organizá-los em uma determinada ordem para facilitar sua utilização. Essa organização é chamada de ordenação.

Imagine, por exemplo, uma lista com as notas de vários alunos:

```text
7, 3, 9, 5, 6
```

Podemos organizar esses valores em ordem crescente:

```text
3, 5, 6, 7, 9
```

Ou em ordem decrescente:
```text
9, 7, 6, 5, 3
```

mesmo pode acontecer com nomes, preços, idades, códigos de produtos, datas ou qualquer outro dado que possa ser comparado.

Um algoritmo de ordenação é um conjunto de passos utilizado para reorganizar os elementos de uma estrutura de dados de acordo com um determinado critério.

## Por que ordenar os dados?

A ordenação pode tornar os dados mais fáceis de visualizar, analisar e utilizar. Uma lista de produtos, por exemplo, pode ser organizada pelo preço; uma lista de alunos pode ser organizada pelo nome ou pela nota; e uma lista de compromissos pode ser organizada pela data.

Além disso, a ordenação pode contribuir para que determinadas operações sejam realizadas de maneira mais eficiente. Em algumas situações, quando os dados estão organizados, podemos utilizar estratégias de busca que evitam verificar todos os elementos um por um.

A ordenação não serve apenas para deixar as informações visualmente organizadas para o usuário; ela é um **mecanismo fundamental de otimização e eficiência** no desenvolvimento de programas:

1. **Acelera a busca por informações:** Em uma coleção desordenada, localizar um dado pode exigir a verificação de cada um dos itens. Quando a coleção está previamente ordenada, o programa pode utilizar métodos de busca que dividem o conjunto sucessivamente, reduzindo drasticamente a quantidade de comparações e o tempo de processamento necessários para encontrar o elemento.
2. **Simplifica a identificação de duplicatas e agrupamentos:** Em uma lista ordenada, elementos iguais ou pertencentes ao mesmo grupo ficam posicionados lado a lado. Isso permite filtrar repetições ou consolidar estatísticas de maneira direta durante uma única leitura dos dados.
3. **Prepara dados para etapas subsequentes:** Diversos módulos de sistemas — como processamento financeiro, emissão de relatórios hierárquicos e análises estatísticas — exigem que as informações estejam ordenadas como pré-requisito para funcionarem sem sobrecarregar a memória e o processador do computador.

## Ordenar também tem um custo

É importante perceber que organizar os dados não acontece de graça. Para colocar os elementos na ordem desejada, o computador precisa realizar operações, como comparar valores e, dependendo da situação, trocar elementos de posição.

Por isso, ao estudar algoritmos de ordenação, não devemos nos preocupar apenas com "qual algoritmo funciona?", mas também com "quantas operações ele precisa realizar?".

Quando temos poucos elementos, essa diferença pode ser praticamente imperceptível. Porém, imagine uma lista contendo milhares ou milhões de valores. Um algoritmo que realiza operações desnecessárias pode levar muito mais tempo para concluir a mesma tarefa.

## Bubble Sort

O Bubble Sort percorre a lista comparando elementos que estão lado a lado.

Se eles estiverem na ordem errada, são trocados de posição. Esse processo é conhecido como SWAP.

Por exemplo, considerando uma ordenação crescente:

```Text
[5, 2, 8, 1]
```

Começamos comparando os dois primeiros:
```Text
5 > 2
```

Então trocamos:
```Text
[2, 5, 8, 1]
```

Depois comparamos:
```Text
5 < 8
```

Não precisamos trocar:
```Text
[2, 5, 8, 1]
```

Depois:
```Text
8 > 1
```

Trocamos:
```Text
[2, 5, 1, 8]
```

Perceba algo importante: **o maior elemento acabou chegando ao final da lista.** Esse processo continua sendo repetido até que todos os elementos estejam na posição correta.

**Importante:** Na próxima vez que o algoritmo retornar ao início da lista, **ele não visitará mais a última casa**. Isso por que na primeira vez que executou, o algoritmo Bubble Sort já colocou o maior elemento no final da lista, logo não há necessidade de passar por essa última posição novamente.

### Algoritmo Bubble Sort
 ```python
 numeros = [5, 2, 8, 1, 4]

for i in range(len(numeros)):
    for j in range(len(numeros) - 1 - i):

        if numeros[j] > numeros[j + 1]:
            numeros[j], numeros[j + 1] = numeros[j + 1], numeros[j]

print(numeros)
```

O Bubble Sort normalmente utiliza duas repetições:

- uma para controlar as várias passagens pela lista;
- outra para percorrer os elementos e realizar as comparações.

### Complexidade

Considerando que n é o tamanho da lista, precisamos percorrer todas as casas fazendo n-1 vezes acessos (um acesso para cada casa). A cada acesso temos que percorrer a lista comparando os valores e 'empurrando' o maior valor para o final. Para isso, realizamos outro laço que será o responsável por fazer n-1 vezes as comparações. Logo temos:

```text
(n-1) x (n-1)
  |       ↓
  ↓       Comparar
  Percorrer
```

Logo:

```text
(n-1) x (n-1) = n² -2n + 1
```

Para utilizar a notação de complexidade, desconsideramos as constantes e os valores com os menores índices. Desta forma, temos:


```text
n² -2n + 1 = n².
Escrevemos no formato denotação: O(n²). 
```