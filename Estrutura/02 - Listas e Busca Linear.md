# Estrutura de Dados

## Listas e Busca Linear

---

# 1. Introdução

Uma das primeiras necessidades que encontramos ao programar é a de trabalhar com **vários dados relacionados**.

Imagine que precisamos armazenar os nomes de cinco alunos:

```python
nome1 = "Ana"
nome2 = "Carlos"
nome3 = "João"
nome4 = "Maria"
nome5 = "Pedro"
```

O programa funciona.

Mas imagine agora que precisamos armazenar 100 alunos.

Ou 1.000.

Ou 100.000.

Ter uma variável diferente para cada elemento rapidamente se torna inviável.

Precisamos de uma maneira de **organizar vários valores em uma única estrutura**.

É nesse contexto que aparecem as **listas**.

---

# 2. O que é uma lista?

Uma lista é uma estrutura que permite armazenar **vários elementos em uma única variável**, mantendo esses elementos em uma sequência.

Em Python:

```python
alunos = ["Ana", "Carlos", "João", "Maria", "Pedro"]
```

Podemos visualizar essa lista assim:

```text
Índice:    0        1         2        3        4
           ↓        ↓         ↓        ↓        ↓
        +------+----------+-------+--------+--------+
Lista:  | Ana  | Carlos   | João  | Maria  | Pedro  |
        +------+----------+-------+--------+--------+
```

Cada elemento ocupa uma determinada posição.

Essa posição é chamada de **índice**.

---

# 3. Índices

Em Python, os índices começam em `0`.

Portanto:

```python
alunos = ["Ana", "Carlos", "João", "Maria", "Pedro"]
```

Temos:

```text
Ana     → índice 0
Carlos  → índice 1
João    → índice 2
Maria   → índice 3
Pedro   → índice 4
```

Podemos acessar um elemento utilizando seu índice:

```python
print(alunos[0])
```

Resultado:

```text
Ana
```

Outro exemplo:

```python
print(alunos[3])
```

Resultado:

```text
Maria
```

Uma forma simples de lembrar:

> **O índice representa a posição do elemento dentro da lista.**

---

# 4. Por que o índice começa em zero?

Essa é uma das primeiras coisas que costuma causar estranheza.

Se temos:

```python
alunos = ["Ana", "Carlos", "João"]
```

podemos pensar:

```text
posição humana:
1 → Ana
2 → Carlos
3 → João
```

Mas Python utiliza:

```text
índice:
0 → Ana
1 → Carlos
2 → João
```

Assim, o índice indica quantas posições precisamos avançar a partir do início da lista.

```text
        início
          ↓
        [Ana] [Carlos] [João]
          0      1       2
```

Depois de algum tempo, o zero deixa de parecer tão estranho. Ele apenas está fazendo seu trabalho silenciosamente.

---

# 5. Tamanho da lista

Podemos descobrir quantos elementos existem utilizando `len()`:

```python
alunos = ["Ana", "Carlos", "João", "Maria", "Pedro"]

print(len(alunos))
```

Resultado:

```text
5
```

É importante diferenciar:

```text
Quantidade de elementos → 5
Maior índice            → 4
```

Isso acontece porque os índices começam em `0`.

Podemos representar:

```text
len(lista)   → quantidade de elementos

maior índice → len(lista) - 1
```

---

# 6. Percorrendo uma lista

Uma das operações mais importantes ao trabalhar com listas é **percorrer seus elementos**.

Podemos utilizar um `for`:

```python
alunos = ["Ana", "Carlos", "João", "Maria", "Pedro"]

for aluno in alunos:
    print(aluno)
```

Resultado:

```text
Ana
Carlos
João
Maria
Pedro
```

Nesse caso, o Python fornece diretamente cada elemento da lista.

---

# 7. Percorrendo utilizando índices

Também podemos percorrer a lista utilizando os índices:

```python
alunos = ["Ana", "Carlos", "João", "Maria", "Pedro"]

for i in range(len(alunos)):
    print(alunos[i])
```

Podemos visualizar o funcionamento:

```text
i = 0 → alunos[0] → Ana
i = 1 → alunos[1] → Carlos
i = 2 → alunos[2] → João
i = 3 → alunos[3] → Maria
i = 4 → alunos[4] → Pedro
```

Essa forma é especialmente importante quando precisamos conhecer **a posição do elemento**, além do seu valor.

---

# 8. Elemento e índice são coisas diferentes

Considere:

```python
numeros = [10, 20, 30, 40]
```

Temos:

```text
Índice:    0    1    2    3
           ↓    ↓    ↓    ↓
Valor:    10   20   30   40
```

O `2` é o índice.

O `30` é o valor armazenado nessa posição.

Portanto:

```python
numeros[2]
```

significa:

> "Acesse o elemento que está no índice 2."

O resultado será:

```text
30
```

---

# 9. Alterando um elemento

Podemos alterar o valor armazenado em determinada posição:

```python
alunos = ["Ana", "Carlos", "João"]

alunos[1] = "Marcos"
```

Agora temos:

```text
Índice:    0        1        2
           ↓        ↓        ↓
         [Ana]  [Marcos]  [João]
```

A lista continua tendo três elementos.

Apenas modificamos o valor associado ao índice `1`.

---

# 10. Inserindo elementos

Uma lista pode receber novos elementos.

Por exemplo:

```python
alunos = ["Ana", "Carlos", "João"]

alunos.append("Maria")
```

Agora:

```text
[Ana] [Carlos] [João] [Maria]
```

O método `append()` adiciona um elemento ao final da lista.

Também podemos inserir um elemento em determinada posição utilizando `insert()`:

```python
alunos.insert(1, "Pedro")
```

Nesse caso, o elemento será inserido no índice `1`.

---

# 11. Removendo elementos

Também podemos remover elementos.

Por exemplo:

```python
alunos.remove("Carlos")
```

O método `remove()` procura o valor informado e remove sua ocorrência correspondente.

Também podemos remover utilizando o índice:

```python
del alunos[1]
```

Nesse caso, estamos dizendo:

> "Remova o elemento que está no índice 1."

É importante perceber que existem diferentes maneiras de manipular uma lista.

A escolha depende daquilo que o problema exige.

---

# 12. Listas e diferentes tipos de dados

Em Python, uma lista pode armazenar diferentes tipos de valores:

```python
dados = [10, "João", 7.5, True]
```

Entretanto, em muitos problemas de Estrutura de Dados, trabalharemos com listas nas quais os elementos possuem características semelhantes:

```python
idades = [18, 21, 19, 25, 20]
```

ou:

```python
nomes = ["Ana", "Carlos", "João", "Maria"]
```

Isso facilita o raciocínio sobre as operações que serão realizadas.

---

# 13. O principal desafio: encontrar um elemento

Agora imagine que temos:

```python
numeros = [12, 45, 7, 23, 91, 34, 18]
```

E queremos descobrir se o número `23` está na lista.

Uma possibilidade é verificar os elementos um por um:

```text
12 → não é 23
45 → não é 23
7  → não é 23
23 → encontrado!
```

Essa estratégia é chamada de **Busca Linear**.

---

# 14. O que é Busca Linear?

A busca linear é uma estratégia na qual analisamos os elementos **sequencialmente**, normalmente começando pelo primeiro.

A ideia básica é:

```text
Primeiro elemento
       ↓
é o elemento procurado?
       ↓
      não
       ↓
Próximo elemento
       ↓
é o elemento procurado?
       ↓
      não
       ↓
Próximo elemento
       ↓
      ...
```

Continuamos até:

1. encontrar o elemento; ou
2. chegar ao final da lista.

---

# 15. Exemplo de Busca Linear

Considere:

```python
numeros = [15, 8, 27, 42, 19, 31]
```

Queremos encontrar:

```text
42
```

A busca pode ser representada assim:

```text
[15] [8] [27] [42] [19] [31]
  ↓
 15 == 42?
 Não

      ↓
[15] [8] [27] [42] [19] [31]
       ↓
 8 == 42?
 Não

            ↓
[15] [8] [27] [42] [19] [31]
            ↓
 27 == 42?
 Não

                  ↓
[15] [8] [27] [42] [19] [31]
                  ↓
 42 == 42?
 SIM!
```

O algoritmo encontrou o valor no quarto elemento analisado.

---

# 16. Implementando uma Busca Linear

Uma implementação simples pode ser:

```python
numeros = [15, 8, 27, 42, 19, 31]

procurado = 42

encontrado = False

for numero in numeros:
    if numero == procurado:
        encontrado = True
        break

if encontrado:
    print("Elemento encontrado")
else:
    print("Elemento não encontrado")
```

A lógica é:

```text
encontrado = False
       ↓
Percorrer a lista
       ↓
Comparar cada elemento
       ↓
Encontrou?
  ↙       ↘
SIM       NÃO
 ↓         ↓
True      continua
 ↓
break
```

---

# 17. Por que utilizar uma variável como `encontrado`?

A variável:

```python
encontrado = False
```

funciona como uma espécie de indicador.

Inicialmente:

```text
encontrado = False
```

Se encontrarmos o elemento:

```python
encontrado = True
```

Depois do percurso, podemos verificar o estado dessa variável.

Esse tipo de variável é frequentemente chamado de **flag**, ou indicador de estado.

---

# 18. Busca Linear retornando a posição

Muitas vezes não queremos apenas saber se o elemento existe.

Queremos saber **em qual posição ele está**.

Podemos fazer:

```python
numeros = [15, 8, 27, 42, 19, 31]

procurado = 42

posicao = -1

for i in range(len(numeros)):
    if numeros[i] == procurado:
        posicao = i
        break

if posicao != -1:
    print("Elemento encontrado no índice:", posicao)
else:
    print("Elemento não encontrado")
```

Resultado:

```text
Elemento encontrado no índice: 3
```

---

# 19. Por que utilizar `-1`?

Nesse exemplo:

```python
posicao = -1
```

representa inicialmente:

> "Ainda não encontrei o elemento."

Como os índices válidos da lista são:

```text
0, 1, 2, 3, ...
```

podemos utilizar `-1` como um indicador de que a busca não encontrou uma posição válida.

Assim:

```text
posicao == -1
```

significa:

```text
não encontrado
```

Enquanto:

```text
posicao >= 0
```

indica que encontramos uma posição válida.

---

# 20. Busca Linear em uma função

Podemos transformar o algoritmo em uma função:

```python
def buscar(lista, procurado):

    for i in range(len(lista)):

        if lista[i] == procurado:
            return i

    return -1
```

Podemos utilizar:

```python
numeros = [15, 8, 27, 42, 19, 31]

posicao = buscar(numeros, 42)

print(posicao)
```

Resultado:

```text
3
```

A função retorna o índice onde o elemento foi encontrado.

Se não encontrar:

```python
posicao = buscar(numeros, 100)
```

teremos:

```text
-1
```

---

# 21. Como a função funciona?

Considere:

```python
buscar([15, 8, 27, 42], 42)
```

O algoritmo executará aproximadamente:

```text
i = 0
lista[0] == 42?
15 == 42 → Não

i = 1
lista[1] == 42?
8 == 42 → Não

i = 2
lista[2] == 42?
27 == 42 → Não

i = 3
lista[3] == 42?
42 == 42 → SIM

return 3
```

O `return` encerra a função imediatamente.

Isso evita continuar percorrendo elementos depois que o valor já foi encontrado.

---

# 22. E se o elemento não existir?

Considere:

```python
numeros = [15, 8, 27, 42]
```

E procuramos:

```text
100
```

A busca fará:

```text
15 == 100? → Não
8  == 100? → Não
27 == 100? → Não
42 == 100? → Não
```

Chegamos ao final da lista sem encontrar o elemento.

Nesse caso:

```python
return -1
```

indica que a busca não obteve sucesso.

---

# 23. Melhor e pior caso

Uma característica importante da busca linear é que a quantidade de elementos analisados depende da posição do elemento procurado.

Considere:

```text
[10] [20] [30] [40] [50] [60]
```

Se procurarmos `10`:

```text
10 → encontrado imediatamente
```

Poucos elementos foram analisados.

Agora procure:

```text
60
```

Será necessário verificar:

```text
10
20
30
40
50
60
```

Todos os elementos foram analisados.

E se procurarmos:

```text
100
```

também precisaremos verificar todos os elementos para concluir que ele não está na lista.

---

# 24. Quantidade de comparações

Considere uma lista com `n` elementos.

Na busca linear:

### Melhor caso

O elemento está logo no início.

```text
aproximadamente 1 comparação
```

### Pior caso

O elemento está no final ou não existe.

```text
aproximadamente n comparações
```

Portanto, no pior caso, quanto maior a lista, maior pode ser a quantidade de elementos que precisamos analisar.

---

# 25. Complexidade da Busca Linear

Quando analisamos a complexidade da busca linear, podemos representá-la por:

```text
O(n)
```

Isso significa que o número de operações cresce de maneira proporcional à quantidade de elementos que pode precisar ser analisada.

Por exemplo:

```text
10 elementos  → até aproximadamente 10 verificações
100 elementos → até aproximadamente 100 verificações
1.000 elementos → até aproximadamente 1.000 verificações
```

A ideia principal é:

> **No pior caso, podemos precisar percorrer toda a lista.**

---

# 26. O que acontece quando a lista cresce?

Imagine uma lista pequena:

```text
[10, 20, 30, 40, 50]
```

Percorrê-la é rápido.

Agora imagine:

```text
[10, 20, 30, ... milhares de elementos ...]
```

Se o elemento procurado estiver no final, ou não existir, o algoritmo precisará analisar muitos elementos.

É por isso que a análise de complexidade é importante.

Não estamos preocupados apenas com:

> "O algoritmo funciona?"

Também precisamos perguntar:

> **"Como ele se comporta quando a quantidade de dados aumenta?"**

---

# 27. Busca Linear e listas

A busca linear combina naturalmente com listas porque podemos percorrer seus elementos sequencialmente.

A ideia pode ser resumida:

```text
LISTA
  ↓
percorrer elementos
  ↓
comparar com o valor procurado
  ↓
encontrou?
 ↙     ↘
SIM     NÃO
 ↓       ↓
retorna  continua
posição  busca
```

É uma estratégia simples, direta e muito importante para compreender algoritmos de busca.

---

# 28. Casos que precisam ser considerados

Ao implementar uma busca, não pense apenas no caso normal.

Teste situações diferentes.

## Lista com vários elementos

```python
numeros = [10, 20, 30, 40, 50]
```

## Elemento no início

```text
procurar 10
```

## Elemento no meio

```text
procurar 30
```

## Elemento no final

```text
procurar 50
```

## Elemento inexistente

```text
procurar 100
```

## Lista com apenas um elemento

```python
numeros = [10]
```

## Lista vazia

```python
numeros = []
```

Esses testes ajudam a verificar se o algoritmo realmente foi compreendido.

---

# 29. Lista vazia

Considere:

```python
numeros = []
```

Não existe nenhum elemento para analisar.

Mesmo assim, uma boa implementação da busca deve funcionar corretamente.

Por exemplo:

```python
def buscar(lista, procurado):

    for i in range(len(lista)):

        if lista[i] == procurado:
            return i

    return -1
```

Se:

```python
buscar([], 10)
```

o `for` simplesmente não terá elementos para percorrer.

A função chegará ao:

```python
return -1
```

Portanto:

```text
-1 → elemento não encontrado
```

---

# 30. Uma implementação mais simples

Também podemos fazer uma busca linear utilizando diretamente os valores:

```python
def buscar(lista, procurado):

    for elemento in lista:

        if elemento == procurado:
            return True

    return False
```

Nesse caso, a função responde apenas:

```text
True
```

ou:

```text
False
```

A diferença está no que o problema exige.

Se precisamos apenas saber se existe:

```text
True / False
```

pode ser suficiente.

Se precisamos saber a posição:

```text
índice
```

devemos guardar ou retornar essa informação.

---

# 31. O algoritmo depende do problema

Considere estas duas perguntas:

### Problema A

> O aluno está cadastrado?

Podemos responder:

```text
True
False
```

### Problema B

> Em qual posição o aluno está cadastrado?

Precisamos retornar:

```text
índice
```

A busca é semelhante nos dois casos.

O que muda é a **informação que precisamos obter como resultado**.

Isso é importante em programação:

> **O algoritmo deve ser construído de acordo com o problema que precisa ser resolvido.**

---

# 32. O que devemos aprender com listas e Busca Linear?

O objetivo desse conteúdo vai além de saber utilizar:

```python
lista.append()
```

ou escrever:

```python
for i in range(len(lista)):
```

É importante compreender:

* como os dados são organizados;
* o que é um índice;
* como acessar elementos;
* como percorrer uma lista;
* como inserir elementos;
* como remover elementos;
* como modificar elementos;
* como procurar informações;
* como controlar uma busca;
* como tratar o caso em que o elemento não existe;
* como identificar melhor e pior caso;
* como analisar o crescimento do custo do algoritmo.

---

# 33. Checklist de aprendizagem

Antes de avançar para o próximo conteúdo, verifique se você consegue:

* [ ] Explicar o que é uma lista.
* [ ] Criar uma lista em Python.
* [ ] Explicar o que é um índice.
* [ ] Acessar um elemento pelo índice.
* [ ] Descobrir o tamanho da lista.
* [ ] Percorrer uma lista com `for`.
* [ ] Percorrer uma lista utilizando índices.
* [ ] Alterar um elemento.
* [ ] Inserir um elemento.
* [ ] Remover um elemento.
* [ ] Explicar o funcionamento da Busca Linear.
* [ ] Implementar uma Busca Linear.
* [ ] Informar se um elemento foi encontrado.
* [ ] Retornar a posição de um elemento.
* [ ] Tratar o caso em que o elemento não existe.
* [ ] Tratar uma lista vazia.
* [ ] Identificar o melhor caso.
* [ ] Identificar o pior caso.
* [ ] Explicar por que a Busca Linear possui complexidade `O(n)` no pior caso.
* [ ] Explicar o próprio código sem simplesmente lê-lo linha por linha.

---

# 34. Resumo

Podemos resumir o conteúdo da seguinte maneira:

```text
LISTA
  ↓
Organiza vários elementos
  ↓
Cada elemento possui um índice
  ↓
Podemos acessar e modificar elementos
  ↓
Podemos percorrer os elementos
  ↓
Podemos procurar elementos
  ↓
BUSCA LINEAR
  ↓
Percorre os elementos sequencialmente
  ↓
Compara cada elemento com o procurado
  ↓
Para quando encontra
  ↓
Ou termina quando chega ao final
```

A Busca Linear é uma estratégia simples, mas representa um conceito fundamental:

> **Para resolver um problema, precisamos definir uma sequência de passos que permita analisar os dados e chegar a uma resposta.**

E essa ideia será importante durante toda a disciplina.

---

# 35. Exercício de fixação

Considere a seguinte lista:

```python
numeros = [17, 4, 29, 8, 13, 42, 6]
```

Implemente uma função chamada `buscar()` que receba:

* uma lista;
* um valor que deverá ser procurado.

A função deverá:

1. percorrer a lista;
2. verificar cada elemento;
3. retornar o índice onde o valor foi encontrado;
4. retornar `-1` caso o valor não exista.

Teste pelo menos:

```text
17
42
6
100
```

Depois teste também:

```python
numeros = []
```

e:

```python
numeros = [50]
```

### Desafio

Depois de implementar a função, tente explicar, sem olhar o código:

> **O que acontece dentro da função quando o elemento procurado está no primeiro índice?**

E depois:

> **O que acontece quando o elemento não existe na lista?**

Se você consegue explicar o comportamento do algoritmo, e não apenas reproduzir o código, está estudando da maneira certa.
