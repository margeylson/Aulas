# Quick Sort

O **Quick Sort** é um algoritmo de ordenação utilizado para organizar os elementos de uma coleção. Seu funcionamento é baseado na estratégia de **dividir para conquistar**, na qual um problema maior é dividido em problemas menores que podem ser resolvidos utilizando a mesma lógica.

A ideia central do Quick Sort é escolher um elemento da lista para ser o **pivô**. A partir dele, os demais elementos são reorganizados de forma que os valores menores fiquem de um lado e os valores maiores fiquem do outro. Depois dessa divisão, o algoritmo aplica novamente o mesmo processo às partes menores da lista.

Por exemplo, considere a lista:

```text
[8, 3, 7, 4, 9, 2, 6]
```

Podemos escolher o valor `4` como pivô. O objetivo do particionamento será separar os elementos em relação a ele:

```text
[3, 2]   4   [8, 7, 9, 6]
```

Nesse momento, é importante perceber que os dois lados ainda não estão necessariamente ordenados. O que foi feito foi apenas separar os elementos menores e maiores que o pivô.

O algoritmo então aplica novamente o mesmo procedimento:

```text
[3, 2]   4   [8, 7, 9, 6]
  ↓                   ↓
ordenar             ordenar
```

A parte `[3, 2]` será dividida novamente, assim como `[8, 7, 9, 6]`. Esse processo continua até que as partes sejam tão pequenas que não precisem mais ser divididas.

Essa característica faz com que a **recursividade** seja bastante natural no Quick Sort. O algoritmo resolve um problema dividindo-o em problemas menores do mesmo tipo.

---

## O pivô

A escolha do pivô é uma das decisões importantes do Quick Sort. Dependendo da implementação, ele pode ser escolhido de diferentes maneiras, como o primeiro elemento, o último elemento ou outro elemento selecionado segundo alguma estratégia.

A escolha do pivô influencia diretamente o comportamento do algoritmo.

Quando o pivô consegue dividir a lista aproximadamente ao meio, temos uma situação favorável:

```text
          lista
         /     \
      metade   metade
       / \       / \
      ... ...   ... ...
```

Nesse cenário, o número de divisões cresce aproximadamente como:

$$
\log_2(n)
$$

Como cada nível precisa analisar os elementos da lista, chegamos a uma complexidade próxima de:

$$
O(n\log n)
$$

Essa é a complexidade característica do Quick Sort em seu **caso médio** e em seu **melhor caso**.

---

## O pior caso

O Quick Sort também pode apresentar um comportamento menos eficiente.

Imagine uma lista já ordenada:

```text
[1, 2, 3, 4, 5, 6, 7]
```

Se o algoritmo escolher sempre um dos extremos como pivô, a divisão pode ficar extremamente desequilibrada:

```text
[1, 2, 3, 4, 5, 6]   7
```

Depois:

```text
[1, 2, 3, 4, 5]   6
```

Depois:

```text
[1, 2, 3, 4]   5
```

Em vez de dividir o problema aproximadamente pela metade, o algoritmo está retirando apenas um elemento por vez.

Nesse caso, a complexidade pode chegar a:

$$
O(n^2)
$$

Portanto, podemos resumir:

| Situação | Complexidade |
|---|---:|
| Melhor caso | $O(n\log n)$ |
| Caso médio | $O(n\log n)$ |
| Pior caso | $O(n^2)$ |

---

## Quick Sort e outros algoritmos

Uma das razões para estudar o Quick Sort é perceber que diferentes algoritmos podem resolver o mesmo problema com desempenhos bastante diferentes.

Algoritmos como **Bubble Sort** e **Insertion Sort** possuem complexidade de $O(n^2)$ em seu pior caso. O Quick Sort, por outro lado, apresenta $O(n\log n)$ em seu comportamento médio.

Essa diferença se torna especialmente importante quando trabalhamos com grandes volumes de dados.

Por exemplo, aumentar uma coleção de 100 para 1.000 elementos representa um aumento de dez vezes na quantidade de dados. Porém, o aumento no trabalho realizado por algoritmos diferentes pode ser muito maior ou menor dependendo de sua complexidade.

É justamente por isso que não basta saber implementar um algoritmo. Em Estrutura de Dados, também precisamos compreender **como ele se comporta quando a quantidade de dados cresce**.

---

## Em resumo

O Quick Sort:

- é um algoritmo de ordenação;
- utiliza a estratégia de **dividir para conquistar**;
- escolhe um elemento chamado **pivô**;
- utiliza o **particionamento** para separar os elementos em relação ao pivô;
- normalmente utiliza **recursividade** para ordenar as partes;
- apresenta $O(n\log n)$ no melhor caso e no caso médio;
- pode chegar a $O(n^2)$ no pior caso;
- pode ser muito eficiente para grandes volumes de dados.

A ideia fundamental pode ser resumida em quatro passos:

```text
1. Escolher um pivô
        ↓
2. Particionar a lista
        ↓
3. Ordenar recursivamente as duas partes
        ↓
4. Obter a lista ordenada
```

Mais do que decorar o código, é importante compreender **por que dividir a lista pode tornar o problema mais fácil de resolver**. Essa é a essência do Quick Sort e também uma das ideias mais importantes da análise de algoritmos.

```python
def quicksort(lista):
    # Caso base: lista com 0 ou 1 elemento já está ordenada
    if len(lista) <= 1:
        return lista

    # 1. Escolher o pivô (aqui, o primeiro elemento)
    pivo = lista[0]

    # 2. Criar listas auxiliares
    menores = []
    maiores = []

    # 3. Percorrer o restante da lista
    for i in range(1, len(lista)):
        elemento = lista[i]

        if elemento <= pivo:
            menores.append(elemento)
        else:
            maiores.append(elemento)

    # 4. Ordenar recursivamente as partes
    lista_menores_ordenada = quicksort(menores)
    lista_maiores_ordenada = quicksort(maiores)

    # 5. Combinar os resultados
    resultado = []

    # adiciona os menores ordenados
    for item in lista_menores_ordenada:
        resultado.append(item)

    # adiciona o pivô
    resultado.append(pivo)

    # adiciona os maiores ordenados
    for item in lista_maiores_ordenada:
        resultado.append(item)

    return resultado

lista_baguncada = [3, 4, 5, 6, 7, 8, 9]

ordenado = quicksort(lista_baguncada)

print(ordenado)
```
