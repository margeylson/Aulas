# Insertion Sort

O **Insertion Sort** é um algoritmo de ordenação que organiza os elementos de uma coleção construindo, aos poucos, uma parte ordenada da lista.

A ideia pode ser comparada à maneira como organizamos cartas na mão. Ao receber uma nova carta, procuramos sua posição correta entre as cartas que já estão organizadas e deslocamos as demais para abrir espaço.

Por isso, o nome **Insertion Sort** pode ser entendido como **ordenação por inserção**.

---

## 1. Ideia principal

Considere a seguinte lista:

```text
[8, 3, 7, 4, 9]
```

O algoritmo começa considerando que o primeiro elemento já está ordenado:

```text
[8] [3, 7, 4, 9]
```

Agora precisamos inserir o `3` na posição correta:

```text
[3, 8] [7, 4, 9]
```

Depois, inserimos o `7`:

```text
[3, 7, 8] [4, 9]
```

Depois o `4`:

```text
[3, 4, 7, 8] [9]
```

Por fim, o `9`:

```text
[3, 4, 7, 8, 9]
```

A cada etapa, uma parte da lista permanece ordenada e o algoritmo insere um novo elemento nessa parte.

---

## 2. Como o algoritmo funciona?

O funcionamento pode ser resumido em quatro passos:

1. Escolher o próximo elemento que será inserido.
2. Compará-lo com os elementos anteriores.
3. Deslocar para a direita os elementos maiores que ele.
4. Inserir o elemento na posição correta.

Podemos representar a ideia da seguinte maneira:

```text
Parte ordenada | Elementos ainda não processados
       ↓                       ↓

[3, 7, 8]      | [4, 9]
```

O próximo elemento será `4`.

O algoritmo compara:

```text
4 < 8 → desloca 8
4 < 7 → desloca 7
4 > 3 → para
```

Depois coloca o `4` na posição encontrada:

```text
[3, 4, 7, 8] | [9]
```

---

## 3. Exemplo passo a passo

Considere:

```text
[8, 3, 7, 4, 9]
```

### Primeira etapa

Consideramos `8` como parte ordenada:

```text
[8] | [3, 7, 4, 9]
```

### Segunda etapa

Selecionamos `3`.

Como:

```text
3 < 8
```

o `8` precisa ser deslocado:

```text
[3, 8] | [7, 4, 9]
```

### Terceira etapa

Selecionamos `7`.

Comparamos com `8`:

```text
7 < 8
```

Deslocamos o `8`.

Depois:

```text
7 > 3
```

Portanto, o `7` é inserido entre `3` e `8`:

```text
[3, 7, 8] | [4, 9]
```

### Quarta etapa

Selecionamos `4`.

Comparamos:

```text
4 < 8
```

Deslocamos `8`.

```text
4 < 7
```

Deslocamos `7`.

```text
4 > 3
```

Paramos.

Resultado:

```text
[3, 4, 7, 8] | [9]
```

### Quinta etapa

Selecionamos `9`.

Como:

```text
9 > 8
```

ele já está na posição correta:

```text
[3, 4, 7, 8, 9]
```

---

## 4. Implementação em Python

Uma implementação simples do Insertion Sort pode ser:

```python
def insertion_sort(lista):

    for i in range(1, len(lista)):
        valor = lista[i]
        j = i - 1

        while j >= 0 and lista[j] > valor:
            lista[j + 1] = lista[j]
            j -= 1

        lista[j + 1] = valor
    return lista
```

---

## 5. Entendendo o código

A variável `i` representa a posição do elemento que será inserido:

```python
for i in range(1, len(lista)):
```

Começamos em `1` porque consideramos o primeiro elemento, na posição `0`, como inicialmente ordenado.

Depois armazenamos o elemento:

```python
valor = lista[i]
```

Esse é o valor que estamos tentando colocar na posição correta.

Em seguida:

```python
j = i - 1
```

começamos a comparar o valor com o elemento imediatamente anterior.

Enquanto o elemento anterior for maior:

```python
while j >= 0 and lista[j] > valor:
```

ele será deslocado uma posição para a direita:

```python
lista[j + 1] = lista[j]
```

Depois avançamos para a posição anterior:

```python
j -= 1
```

Quando encontramos a posição correta, inserimos o valor:

```python
lista[j + 1] = valor
```

---

## 6. Por que deslocar em vez de simplesmente trocar?

Essa é uma característica importante do Insertion Sort.

Considere:

```text
[3, 7, 8, 4]
```

Queremos inserir o `4`.

Precisamos abrir espaço entre `3` e `7`.

Primeiro deslocamos:

```text
[3, 7, 8, 8]
```

Depois:

```text
[3, 7, 7, 8]
```

Agora podemos colocar o `4`:

```text
[3, 4, 7, 8]
```

Portanto, o algoritmo utiliza **deslocamentos** para abrir espaço para o elemento que está sendo inserido.

---

## 7. Complexidade

A complexidade do Insertion Sort depende da situação da lista.

### Melhor caso

O melhor caso ocorre quando a lista já está ordenada:

```text
[1, 2, 3, 4, 5, 6]
```

Nesse cenário, cada elemento já está aproximadamente onde deveria estar.

O algoritmo precisa fazer poucas comparações e nenhum deslocamento significativo.

A complexidade é:

```text
O(n)
```

---

### Pior caso

O pior caso ocorre quando a lista está ordenada de forma inversa:

```text
[6, 5, 4, 3, 2, 1]
```

Nesse caso, cada novo elemento precisa ser comparado com vários elementos anteriores e deslocado.

Para cada posição, o trabalho aumenta:

```text
1
2
3
4
5
...
n
```

A quantidade total de operações cresce aproximadamente como:

```text
1 + 2 + 3 + ... + n
```

Essa soma é proporcional a:

```text
n²
```

Portanto:

\[
O(n^2)
\]

---

## 8. Complexidade do Insertion Sort

| Situação | Complexidade |
|---|---:|
| Melhor caso | `O(n)` |
| Caso médio | `O(n²)` |
| Pior caso | `O(n²)` |

---

## 9. Insertion Sort e listas quase ordenadas

Uma característica interessante do Insertion Sort é seu comportamento em listas que já estão próximas da ordenação.

Por exemplo:

```text
[1, 2, 3, 5, 4, 6, 7]
```

Existe apenas um pequeno problema:

```text
5
4
```

O algoritmo consegue corrigir essa situação realizando poucos deslocamentos.

Por isso, o Insertion Sort pode ser uma alternativa interessante quando:

- a lista é pequena;
- a lista já está quase ordenada;
- os dados chegam gradualmente;
- simplicidade de implementação é importante.

---

## 10. Insertion Sort × Bubble Sort

Os dois algoritmos possuem complexidade `O(n²)` no pior caso, mas funcionam de maneiras diferentes.

| Característica | Bubble Sort | Insertion Sort |
|---|---|---|
| Estratégia | Trocas entre vizinhos | Inserção e deslocamento |
| Elementos comparados | Vizinhos | Elemento atual e anteriores |
| Melhor caso | `O(n)` em versões otimizadas | `O(n)` |
| Pior caso | `O(n²)` | `O(n²)` |
| Listas quase ordenadas | Pode ser eficiente | Geralmente muito interessante |
| Implementação | Simples | Simples |

Uma diferença importante é a forma como os elementos são movimentados.

No Bubble Sort:

```text
elemento ↔ elemento vizinho
```

No Insertion Sort:

```text
elementos maiores → deslocam
             ↓
        abre espaço
             ↓
      novo elemento
```

---

## 11. Insertion Sort × Quick Sort

O Insertion Sort possui uma implementação mais simples e apresenta um comportamento interessante em listas pequenas ou quase ordenadas.

O Quick Sort utiliza a estratégia de **dividir para conquistar** e, em seu caso médio, apresenta:

```text
O(n log n)
```

Enquanto o Insertion Sort possui:

```text
O(n²)
```

no caso médio.

Para grandes volumes de dados, o Quick Sort tende a apresentar uma vantagem significativa.

Entretanto, isso não significa que o Quick Sort seja sempre a melhor escolha.

A escolha de um algoritmo depende das características do problema e dos dados.

---

## 12. Principais características

O Insertion Sort:

- é um algoritmo de ordenação;
- utiliza a ideia de **inserção**;
- constrói gradualmente uma parte ordenada da lista;
- utiliza deslocamentos para abrir espaço;
- possui implementação relativamente simples;
- apresenta `O(n)` no melhor caso;
- apresenta `O(n²)` no caso médio;
- apresenta `O(n²)` no pior caso;
- pode ser eficiente para listas pequenas;
- pode ser eficiente para listas quase ordenadas.

---

## 13. Resumo visual

A ideia do Insertion Sort pode ser resumida assim:

```text
        Escolhe um elemento
                ↓
        Compara com anteriores
                ↓
       Elementos maiores?
          ↙           ↘
        SIM            NÃO
         ↓              ↓
     Desloca       Encontrou a
     para direita   posição correta
         ↓              ↓
         └──────┬───────┘
                ↓
       Insere o elemento
                ↓
        Repete o processo
```

---

