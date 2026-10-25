# Busca Binária

A **Busca Binária** é um algoritmo utilizado para localizar um elemento em uma coleção **ordenada**.

Sua principal característica é não precisar verificar os elementos um por um. A cada etapa, o algoritmo analisa o elemento que está no meio da região de busca e descarta aproximadamente metade dos elementos.

Por isso, sua complexidade é:

$$
O(\log_2 n)
$$

Essa característica faz com que a Busca Binária seja especialmente eficiente quando trabalhamos com grandes quantidades de dados.

---

## 1. Pré-requisito: a lista precisa estar ordenada

A Busca Binária depende da organização dos dados.

Considere:

```text
[3, 7, 10, 15, 21, 28, 35, 42, 50]
```

Se queremos procurar o valor `28`, podemos analisar o elemento central.

```text
[3, 7, 10, 15, 21, 28, 35, 42, 50]
                    ↑
                   meio
```

O elemento central é `21`.

Como:

```text
28 > 21
```

sabemos que o valor procurado, caso exista, estará à direita.

Podemos então ignorar:

```text
[3, 7, 10, 15, 21]
```

e continuar procurando apenas em:

```text
[28, 35, 42, 50]
```

Essa é a principal ideia da Busca Binária:

> **A cada comparação, aproximadamente metade dos elementos deixa de fazer parte da busca.**

---

## 2. Como funciona?

A Busca Binária mantém três informações:

- posição inicial da região de busca;
- posição final da região de busca;
- posição central da região de busca.

Podemos representar:

```text
início                meio                 fim
  ↓                    ↓                    ↓
[  3,  7,  10,  15,  21,  28,  35,  42,  50  ]
```

O elemento do meio é comparado com o valor procurado.

Existem três possibilidades:

### O valor foi encontrado

```text
valor procurado == valor do meio
```

A busca termina.

### O valor procurado é menor

```text
valor procurado < valor do meio
```

Continuamos procurando na metade esquerda.

### O valor procurado é maior

```text
valor procurado > valor do meio
```

Continuamos procurando na metade direita.

---

## 3. Exemplo passo a passo

Considere:

```text
[3, 7, 10, 15, 21, 28, 35, 42, 50]
```

Queremos encontrar:

```text
28
```

### Primeira consulta

O meio da lista é:

```text
21
```

Comparação:

```text
28 > 21
```

Portanto, descartamos a metade esquerda.

Restam:

```text
[28, 35, 42, 50]
```

---

### Segunda consulta

O meio da região restante é:

```text
35
```

Comparação:

```text
28 < 35
```

Portanto, descartamos a parte à direita.

Restam:

```text
[28]
```

---

### Terceira consulta

Agora temos:

```text
28
```

Como:

```text
28 == 28
```

o elemento foi encontrado.

Nesse exemplo, encontramos o valor em apenas **3 consultas**.

---

# 4. Implementação em Python

Uma implementação iterativa pode ser:

```python
def busca_binaria(lista, valor):

    inicio = 0
    fim = len(lista) - 1

    while inicio <= fim:

        meio = (inicio + fim) // 2

        if lista[meio] == valor:
            return meio

        elif valor < lista[meio]:
            fim = meio - 1

        else:
            inicio = meio + 1

    return -1
```

A função retorna:

- o índice do elemento, caso ele seja encontrado;
- `-1`, caso o elemento não esteja presente.

---

# 5. Entendendo o código

## Início da busca

```python
inicio = 0
```

A posição inicial da lista é `0`.

---

## Final da busca

```python
fim = len(lista) - 1
```

O último índice da lista é obtido utilizando seu tamanho menos `1`.

Por exemplo:

```text
lista = [10, 20, 30, 40, 50]
```

Possui:

```text
len(lista) = 5
```

Mas seus índices são:

```text
0  1  2  3  4
```

Por isso:

```python
fim = len(lista) - 1
```

resulta em:

```text
fim = 4
```

---

## Encontrando o meio

```python
meio = (inicio + fim) // 2
```

O operador `//` realiza uma divisão inteira.

Se:

```text
inicio = 0
fim = 8
```

temos:

```text
meio = (0 + 8) // 2
meio = 4
```

Portanto, o índice central é `4`.

---

## Verificando se encontrou

```python
if lista[meio] == valor:
    return meio
```

Se o elemento central for o valor procurado, retornamos sua posição.

---

## Procurando à esquerda

Se:

```python
elif valor < lista[meio]:
```

significa que o valor procurado é menor que o elemento central.

Como a lista está ordenada, sabemos que precisamos procurar à esquerda.

Por isso:

```python
fim = meio - 1
```

---

## Procurando à direita

Caso:

```python
else:
```

o valor procurado é maior que o elemento central.

Então devemos procurar à direita:

```python
inicio = meio + 1
```

---

# 6. Por que a lista precisa estar ordenada?

Imagine que temos:

```text
[40, 10, 70, 20, 90, 30, 50]
```

Queremos procurar `30`.

Se analisarmos o elemento central:

```text
20
```

e concluirmos:

```text
30 > 20
```

poderíamos decidir procurar à direita.

Mas isso não garante que `30` esteja lá.

Ele está à esquerda:

```text
[40, 10, 70, 20, 90, 30, 50]
 ↑
```

O problema é que não existe uma relação de ordem que permita eliminar metade dos elementos.

Por isso:

> **A Busca Binária depende da ordenação dos dados para poder descartar uma parte da coleção com segurança.**

---

# 7. Busca Linear × Busca Binária

Considere uma coleção com `1.000.000` de elementos.

Na Busca Linear, no pior caso, podemos precisar verificar:

```text
1.000.000 elementos
```

Sua complexidade é:

$$
O(n)
$$

Na Busca Binária, a cada etapa eliminamos aproximadamente metade da coleção:

```text
1.000.000
500.000
250.000
125.000
62500
...
1
```

Sua complexidade é:

$$
O(\log_2 n)
$$

Para:

$$
n = 1.000.000
$$

temos:

$$
\log_2(1.000.000) \approx 19,93
$$

Ou seja, são necessárias aproximadamente:

```text
20 consultas
```

no pior caso aproximado.

---

# 8. De onde vem o `log n`?

Essa é uma das partes mais importantes para compreender a Busca Binária.

A cada consulta, dividimos a quantidade de elementos aproximadamente pela metade:

$$
n
$$

$$
\frac{n}{2}
$$

$$
\frac{n}{4}
$$

$$
\frac{n}{8}
$$

$$
\frac{n}{16}
$$

e assim por diante.

Depois de `k` divisões:

$$
\frac{n}{2^k}=1
$$

Multiplicando os dois lados por $2^k$:

$$
n=2^k
$$

Agora precisamos descobrir qual é o valor de `k`.

Aplicando logaritmo na base 2:

$$
\log_2(n)=\log_2(2^k)
$$

Utilizando a propriedade dos logaritmos:

$$
\log_2(2^k)=k
$$

Portanto:

$$
\boxed{k=\log_2(n)}
$$

É daí que surge a complexidade:

$$
\boxed{O(\log_2 n)}
$$

---

# 9. Crescimento da Busca Binária

Uma maneira interessante de visualizar o comportamento da Busca Binária é observar quantos elementos podem ser tratados com determinada quantidade de etapas.

| Etapas | Quantidade aproximada de elementos |
|---:|---:|
| 1 | 2 |
| 2 | 4 |
| 3 | 8 |
| 4 | 16 |
| 5 | 32 |
| 10 | 1.024 |
| 20 | 1.048.576 |
| 30 | 1.073.741.824 |

Isso mostra por que o crescimento de `log n` é tão lento.

Com aproximadamente **20 etapas**, conseguimos trabalhar com mais de **1 milhão de elementos**.

---

# 10. Complexidade

A Busca Binária apresenta:

| Situação | Complexidade |
|---|---:|
| Melhor caso | `O(1)` |
| Caso médio | `O(log n)` |
| Pior caso | `O(log n)` |

### Melhor caso

O elemento procurado está justamente no meio da região analisada.

Encontramos imediatamente:

```text
O(1)
```

### Pior caso

Precisamos continuar dividindo a região até chegar ao elemento ou descobrir que ele não existe.

Nesse caso:

```text
O(log n)
```

---

# 11. Busca Binária recursiva

A Busca Binária também pode ser implementada utilizando **recursividade**.

Uma implementação possível é:

```python
def busca_binaria(lista, valor, inicio, fim):

    if inicio > fim:
        return -1

    meio = (inicio + fim) // 2

    if lista[meio] == valor:
        return meio

    if valor < lista[meio]:
        return busca_binaria(
            lista,
            valor,
            inicio,
            meio - 1
        )

    return busca_binaria(
        lista,
        valor,
        meio + 1,
        fim
    )
```

A ideia é a mesma da versão iterativa.

A diferença está na maneira como o algoritmo repete o processo.

Na versão iterativa:

```text
while
```

Na versão recursiva:

```text
função chama a própria função
```

---

# 12. Quando utilizar a Busca Binária?

A Busca Binária é especialmente interessante quando:

- os dados estão ordenados;
- precisamos realizar muitas consultas;
- a quantidade de dados é grande;
- o acesso aos elementos permite localizar rapidamente a posição central.

Um cenário típico seria:

```text
Lista grande
      ↓
Ordenação
      ↓
Muitas buscas
      ↓
Busca Binária
```

Se tivermos apenas uma pequena quantidade de dados, a simplicidade da Busca Linear pode ser suficiente.

---

# 13. Uma observação importante

É tentador concluir:

> "Busca Binária é sempre melhor que Busca Linear."

Isso não é necessariamente verdade.

A Busca Binária exige uma coleção **ordenada**.

Se os dados estiverem desordenados e houver apenas uma busca, ordenar a coleção primeiro pode custar mais trabalho do que simplesmente percorrê-la.

Por outro lado, se tivermos:

```text
1.000.000 de elementos
+
milhares de consultas
```

pode fazer sentido investir na ordenação inicial para depois realizar as consultas utilizando Busca Binária.

Portanto, a escolha do algoritmo depende do problema.

---

# 14. Busca Binária em resumo

A Busca Binária:

- trabalha sobre uma coleção ordenada;
- verifica o elemento central da região de busca;
- elimina aproximadamente metade dos elementos a cada etapa;
- pode ser implementada de forma iterativa;
- também pode ser implementada de forma recursiva;
- possui complexidade `O(log n)` no caso médio e no pior caso;
- possui complexidade `O(1)` no melhor caso;
- é especialmente eficiente para grandes volumes de dados.

A ideia pode ser resumida em quatro passos:

```text
1. Encontrar o meio
        ↓
2. Comparar com o valor procurado
        ↓
3. Escolher esquerda ou direita
        ↓
4. Repetir até encontrar ou esgotar a busca
```

---


# 16. A Busca Binária em uma frase

> **A Busca Binária encontra elementos em uma coleção ordenada dividindo sucessivamente o espaço de busca pela metade, apresentando complexidade `O(log n)` no caso médio e no pior caso.**
