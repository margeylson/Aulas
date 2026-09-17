# Estrutura de Dados

## Guia de Referência para os Estudos

---

## 1. O que é a disciplina de Estrutura de Dados?

Quando começamos a programar, normalmente aprendemos a criar variáveis, utilizar `if`, `for`, `while`, funções e outras estruturas básicas.

Nesse momento, muitos problemas parecem simples:

```python
nome = "João"
idade = 20
```

ou:

```python
for numero in numeros:
    print(numero)
```

Mas os problemas reais de programação rapidamente começam a crescer.

Imagine, por exemplo, que um sistema precise armazenar:

* 10 produtos;
* 10.000 produtos;
* 1 milhão de produtos;
* milhões de registros que precisam ser pesquisados, ordenados ou modificados.

A pergunta deixa de ser apenas:

> "Como faço o programa funcionar?"

E passa a ser:

> "Como organizo os dados e construo o algoritmo para que o programa continue funcionando bem quando a quantidade de dados crescer?"

É justamente nesse ponto que entra a **Estrutura de Dados**.

---

# 2. Por que as Estruturas de Dados existem?

Uma estrutura de dados é uma forma de **organizar e armazenar informações para que determinadas operações possam ser realizadas de maneira adequada**.

Não existe uma única forma "correta" de armazenar todos os dados.

A melhor organização depende do problema que queremos resolver.

Por exemplo:

### Lista

Pode ser interessante quando precisamos armazenar vários elementos e percorrê-los:

```text
[10, 20, 30, 40, 50]
```

### Pilha

É adequada quando precisamos trabalhar com a ideia:

> O último que entra é o primeiro que sai.

```text
    30  ← topo
    20
    10
```

### Fila

É adequada quando queremos:

> O primeiro que entra é o primeiro que sai.

```text
10 → 20 → 30 → 40
↑
primeiro
```

### Árvore

É útil quando os dados possuem uma relação hierárquica ou quando queremos organizar informações de determinadas maneiras para facilitar operações de busca, inserção e remoção.

```text
           50
         /    \
       30      70
      /  \    /  \
    20   40  60   80
```

Perceba que as estruturas não existem simplesmente porque alguém decidiu criar vários conceitos para complicar a vida dos estudantes.

Elas existem porque **diferentes problemas exigem diferentes formas de organização dos dados**.

---

# 3. Estrutura de Dados não é apenas "guardar informações"

Um erro comum é pensar:

> "Estrutura de Dados serve para guardar dados."

Isso está correto, mas é incompleto.

O mais importante é pensar:

> **Como os dados serão organizados para que as operações necessárias sejam realizadas de maneira adequada?**

Considere uma aplicação que possui 1.000.000 de clientes.

Se precisarmos procurar um cliente, podemos simplesmente verificar um por um:

```text
Cliente 1
Cliente 2
Cliente 3
Cliente 4
...
Cliente 1.000.000
```

Dependendo da organização dos dados, isso pode exigir muitas comparações.

Por outro lado, existem estratégias que permitem reduzir drasticamente a quantidade de elementos que precisam ser analisados.

É aí que entram conceitos como:

* busca linear;
* busca binária;
* árvores;
* ordenação;
* recursividade;
* complexidade de algoritmos.

Portanto:

> **Estrutura de Dados está diretamente relacionada aos algoritmos que manipulam esses dados.**

---

# 4. Estrutura de Dados + Algoritmos

É importante entender que **estrutura de dados e algoritmo estão profundamente relacionados**.

Podemos pensar em:

```text
        PROBLEMA
            ↓
        Como representar os dados?
            ↓
        ESTRUTURA DE DADOS
            ↓
        Como manipular esses dados?
            ↓
        ALGORITMO
            ↓
        SOLUÇÃO
```

Uma estrutura de dados define uma maneira de organizar os dados.

Um algoritmo define uma sequência de passos para resolver um problema.

A escolha da estrutura pode facilitar ou dificultar a construção do algoritmo.

---

# 5. Por que aprender algoritmos mais complexos?

No início da programação, é comum resolver problemas seguindo uma sequência simples:

```text
ler dados
↓
processar dados
↓
mostrar resultado
```

Porém, problemas maiores exigem estratégias mais elaboradas.

Imagine que você tenha 1.000.000 de números e precise descobrir se determinado número está presente.

Uma solução simples seria verificar:

```text
1º elemento
2º elemento
3º elemento
4º elemento
...
```

Essa solução funciona.

Mas funcionar não significa necessariamente ser uma boa solução.

Agora imagine que os dados estejam organizados e que exista uma estratégia capaz de eliminar aproximadamente metade dos elementos analisados a cada etapa.

O algoritmo pode se tornar muito mais eficiente.

Esse é um dos grandes objetivos da disciplina:

> **Aprender a desenvolver soluções que não apenas funcionem, mas que sejam adequadas ao tamanho e às características do problema.**

---

# 6. O computador é rápido. Então por que se preocupar com eficiência?

Uma dúvida comum é:

> "Se o computador é muito rápido, por que precisamos estudar eficiência?"

Porque a quantidade de dados também pode ser muito grande.

Imagine dois algoritmos:

```text
Algoritmo A → realiza aproximadamente n operações
Algoritmo B → realiza aproximadamente n² operações
```

Para poucos elementos, talvez a diferença seja pequena.

Mas considere:

```text
n = 10

A → aproximadamente 10 operações
B → aproximadamente 100 operações
```

Agora:

```text
n = 1.000

A → aproximadamente 1.000 operações
B → aproximadamente 1.000.000 operações
```

E:

```text
n = 1.000.000

A → aproximadamente 1.000.000 operações
B → aproximadamente 1.000.000.000.000 operações
```

O computador continua sendo rápido.

O problema é que **um algoritmo inadequado pode gerar uma quantidade gigantesca de trabalho**.

Por isso, aprender Estrutura de Dados significa também aprender a pensar sobre o comportamento dos algoritmos.

---

# 7. Pensamento algorítmico

Uma das habilidades mais importantes desenvolvidas nesta disciplina é o **pensamento algorítmico**.

Pensar algoritmicamente significa aprender a:

1. compreender o problema;
2. identificar os dados envolvidos;
3. identificar as operações necessárias;
4. dividir problemas grandes em partes menores;
5. encontrar padrões;
6. escolher estratégias;
7. analisar diferentes soluções;
8. avaliar o custo dessas soluções;
9. implementar a solução;
10. testar e corrigir o algoritmo.

Programar não é apenas escrever código.

Antes do código existe o **raciocínio que determina qual código deve ser escrito**.

---

# 8. Resolver problemas difíceis exige abstração

À medida que os problemas aumentam de dificuldade, não podemos depender apenas de decorar códigos.

Precisamos compreender os conceitos.

Por exemplo, ao estudar uma pilha, não é suficiente decorar:

```python
pilha.append(valor)
```

É necessário compreender a ideia:

```text
        TOPO
         ↓
       [30]
       [20]
       [10]
```

Se inserirmos `40`:

```text
       [40] ← TOPO
       [30]
       [20]
       [10]
```

Se retirarmos um elemento, será retirado `40`.

A regra é:

> **LIFO — Last In, First Out**

Ou seja:

> O último elemento inserido é o primeiro a ser removido.

Quando o conceito é compreendido, podemos implementá-lo de diferentes maneiras.

Quando apenas o código é decorado, qualquer pequena mudança no problema pode transformar a solução em um quebra-cabeça.

---

# 9. O objetivo não é decorar algoritmos

Durante a disciplina, você encontrará diversos algoritmos:

* busca linear;
* busca binária;
* bubble sort;
* insertion sort;
* quicksort;
* algoritmos para listas;
* algoritmos para pilhas;
* algoritmos para filas;
* algoritmos para árvores;
* algoritmos recursivos.

É importante conhecer esses algoritmos.

Mas existe uma diferença entre:

> **decorar um algoritmo**

e

> **entender como e por que ele funciona.**

O segundo conhecimento é muito mais importante.

Você deve conseguir responder perguntas como:

* O que o algoritmo está fazendo?
* Por que essa comparação é necessária?
* Por que esse elemento está sendo movimentado?
* O que acontece quando chegamos ao final da estrutura?
* O que acontece quando a estrutura está vazia?
* Qual é o caso-base da recursão?
* Quantas vezes determinado trecho pode ser executado?
* O que acontece se aumentarmos a quantidade de dados?

Essas perguntas desenvolvem raciocínio de programação.

---

# 10. A importância de entender o "porquê"

Considere uma busca binária.

Não basta saber que existe um código parecido com:

```python
meio = (inicio + fim) // 2
```

É necessário entender por que podemos fazer isso.

A busca binária depende de uma característica importante:

> **Os dados precisam estar ordenados.**

A partir disso, podemos comparar o elemento procurado com o elemento central e descartar uma parte dos dados.

Por exemplo:

```text
10  20  30  40  50  60  70  80  90
                ↑
              meio
```

Se procuramos `80`, podemos concluir que não precisamos continuar procurando nos elementos menores que `40`.

O algoritmo não está simplesmente "pulando elementos".

Ele está utilizando uma **propriedade dos dados para eliminar possibilidades**.

Esse tipo de raciocínio é um dos principais objetivos da disciplina.

---

# 11. Complexidade de algoritmos

Outro conceito fundamental é a **complexidade assintótica**.

Ela permite analisar como o custo de um algoritmo cresce conforme aumenta a quantidade de dados.

Uma das notações mais conhecidas é a **Notação Big O**.

Alguns exemplos:

```text
O(1)
O(log n)
O(n)
O(n log n)
O(n²)
```

De maneira simplificada:

| Complexidade | Ideia geral                        |
| ------------ | ---------------------------------- |
| O(1)         | Custo aproximadamente constante    |
| O(log n)     | Crescimento muito lento            |
| O(n)         | Crescimento proporcional aos dados |
| O(n log n)   | Crescimento maior que linear       |
| O(n²)        | Crescimento quadrático             |

O objetivo não é decorar uma tabela.

O objetivo é aprender a perguntar:

> **"Se a quantidade de dados aumentar, o que acontecerá com meu algoritmo?"**

---

# 12. Por que aprender recursividade?

A recursividade aparece quando uma função resolve um problema utilizando uma versão menor do próprio problema.

Um exemplo clássico é o cálculo do fatorial:

```text
5! = 5 × 4 × 3 × 2 × 1
```

Podemos perceber uma estrutura:

```text
5! = 5 × 4!
4! = 4 × 3!
3! = 3 × 2!
...
```

A recursividade é especialmente importante porque aparece naturalmente em estruturas como árvores.

Uma árvore possui subárvores:

```text
          50
        /    \
      30      70
     /  \    /  \
   20   40  60   80
```

Cada parte da árvore pode ser tratada como uma árvore menor.

Portanto, estudar recursividade não é estudar um recurso isolado.

Ela prepara o caminho para compreender algoritmos mais sofisticados.

---

# 13. Estruturas lineares e não lineares

Durante a disciplina, estudaremos diferentes formas de organizar os dados.

## Estruturas lineares

Os elementos podem ser visualizados em uma sequência.

Exemplos:

* listas;
* pilhas;
* filas.

Uma representação simplificada:

```text
A → B → C → D
```

## Estruturas não lineares

Os elementos podem estabelecer relações em diferentes direções ou níveis.

Um exemplo é a árvore:

```text
             A
           /   \
          B     C
        /  \     \
       D    E     F
```

A mudança de estrutura também muda a maneira de pensar nos algoritmos.

---

# 14. Ementa da disciplina

A disciplina possui a seguinte ementa:

> **Representação dos dados, tipos abstratos de dados. Alocação dinâmica de memória. Estrutura de dados lineares: a lista e suas variantes. Recursividade. Busca em Vetores. Pilhas e Filas. Estrutura de dados não-lineares: Árvores. Noções de complexidade assintótica de programas e otimização.**

Durante o curso, esses conteúdos serão trabalhados de maneira progressiva.

Uma possível visão da evolução dos conteúdos é:

```text
Representação dos dados
        ↓
Tipos Abstratos de Dados
        ↓
Alocação dinâmica de memória
        ↓
Listas
        ↓
Recursividade
        ↓
Busca
        ↓
Pilhas e Filas
        ↓
Árvores
        ↓
Complexidade
        ↓
Otimização
```

Os conteúdos não estão isolados.

Eles se conectam.

---

# 15. Carga horária

**Carga Horária: 60 horas**

Como a disciplina possui uma quantidade considerável de conceitos e algoritmos, acompanhar apenas as aulas não é suficiente.

Estrutura de Dados exige prática.

É semelhante ao aprendizado de matemática ou de um instrumento musical: observar alguém resolvendo um problema ajuda, mas não substitui tentar resolver problemas por conta própria.

---

# 16. Avaliações

As avaliações previstas para a disciplina são:

| Avaliação    | Data                |
| ------------ | ------------------- |
| 1ª Avaliação | **29 de outubro**   |
| 2ª Avaliação | **10 de dezembro**  |
| 3ª Avaliação | **18 de fevereiro** |

As datas devem ser utilizadas como referência para organizar os estudos.

Não deixe para estudar Estrutura de Dados apenas na semana da avaliação.

Alguns algoritmos parecem muito simpáticos quando vistos pelo professor no quadro.

Quando aparecem sozinhos no editor de código, podem adquirir uma personalidade bastante diferente.

---

# 17. Como estudar Estrutura de Dados?

A melhor maneira de estudar esta disciplina é combinar:

```text
CONCEITO
   ↓
EXEMPLO
   ↓
IMPLEMENTAÇÃO
   ↓
TESTE
   ↓
EXPLICAÇÃO
   ↓
VARIAÇÃO DO PROBLEMA
```

Não é recomendado estudar apenas lendo códigos.

---

# 18. Etapa 1 — Entenda o conceito

Antes de programar, pergunte:

* O que é essa estrutura?
* Para que ela serve?
* Como seus elementos estão organizados?
* Quais operações podem ser realizadas?
* Quais são as regras dessa estrutura?
* Quais são os casos especiais?

Por exemplo, antes de implementar uma fila:

```text
ENTRA → [A] [B] [C] → SAI
```

Entenda primeiro a regra:

> Primeiro que entra, primeiro que sai.

---

# 19. Etapa 2 — Faça desenhos

Desenhar estruturas de dados é extremamente útil.

Para uma lista:

```text
[10] → [20] → [30] → [40]
```

Para uma pilha:

```text
[30] ← topo
[20]
[10]
```

Para uma fila:

```text
frente                    fim
 ↓                         ↓
[10] → [20] → [30] → [40]
```

Para uma árvore:

```text
          50
        /    \
      30      70
     /  \    /  \
   20   40  60   80
```

O desenho ajuda a transformar um problema abstrato em algo visual.

---

# 20. Etapa 3 — Faça o código manualmente

Depois de compreender o conceito, tente implementar.

Não copie imediatamente o código pronto.

Primeiro tente escrever sua própria solução.

Mesmo que ela apresente erros.

Um erro durante o estudo é informação.

Ele mostra:

> "Existe alguma parte desse conceito que ainda não compreendi completamente."

Nesse momento, investigue o erro.

---

# 21. Etapa 4 — Faça testes pequenos

Ao estudar uma estrutura, comece com poucos elementos.

Por exemplo:

```text
10
20
30
```

Depois teste situações especiais:

```text
estrutura vazia
```

```text
apenas um elemento
```

```text
inserção no início
```

```text
inserção no final
```

```text
remoção do primeiro elemento
```

```text
remoção do último elemento
```

Esses casos ajudam a encontrar erros de lógica.

---

# 22. Etapa 5 — Tente explicar o código

Uma excelente técnica de estudo é explicar o algoritmo em voz alta.

Imagine que alguém pergunte:

> "O que essa linha faz?"

Você precisa conseguir responder.

Depois:

> "Por que ela é necessária?"

E finalmente:

> "O que aconteceria se ela fosse removida?"

Se você consegue explicar o código sem depender de uma leitura linha por linha, provavelmente está começando a compreender o algoritmo.

---

# 23. Etapa 6 — Modifique o problema

Depois que conseguir resolver um exercício, não pare.

Faça pequenas alterações.

Por exemplo:

### Problema original

> Inserir um elemento no final da lista.

Depois tente:

> Inserir no início.

Depois:

> Inserir em uma determinada posição.

Depois:

> Remover determinado elemento.

Depois:

> Inverter a lista.

Cada alteração força você a compreender a estrutura em vez de simplesmente reproduzir uma solução.

---

# 24. Etapa 7 — Tente resolver sem consultar o código

Essa é uma das melhores formas de verificar se realmente aprendeu.

Feche o código.

Pegue uma folha.

Escreva:

```text
1. O que preciso fazer?
2. Quais dados tenho?
3. Qual estrutura estou utilizando?
4. Qual algoritmo posso utilizar?
5. Quais são os casos especiais?
```

Depois tente implementar.

Se esquecer alguma coisa, consulte.

Mas tente novamente depois.

---

# 25. Uma estratégia eficiente de estudo

Uma sessão de estudo pode seguir este modelo:

### 10 minutos — Revisão

Releia o conceito estudado.

Pergunte:

> O que esse conceito resolve?

### 15 minutos — Exemplo

Analise um exemplo pequeno.

Faça desenhos.

Acompanhe as alterações nos dados.

### 25 minutos — Implementação

Escreva o código sozinho.

### 15 minutos — Testes

Teste:

* caso normal;
* estrutura vazia;
* um elemento;
* vários elementos;
* situações de erro.

### 15 minutos — Variação

Altere o problema.

### 10 minutos — Explicação

Explique para você mesmo como o algoritmo funciona.

Uma hora de estudo ativo costuma ser muito mais proveitosa do que uma hora apenas lendo código.

---

# 26. Estude por dificuldade crescente

Não comece sempre pelo exercício mais difícil.

Uma progressão interessante é:

```text
NÍVEL 1
Compreender o conceito
       ↓
NÍVEL 2
Reproduzir uma implementação
       ↓
NÍVEL 3
Implementar sem consultar
       ↓
NÍVEL 4
Modificar o algoritmo
       ↓
NÍVEL 5
Resolver um problema novo
       ↓
NÍVEL 6
Analisar eficiência e complexidade
```

O objetivo é chegar ao nível 5 e, posteriormente, ao nível 6.

---

# 27. Não estude apenas "o código que cai na prova"

Uma armadilha comum é tentar descobrir exatamente qual código será cobrado e decorá-lo.

Isso pode funcionar quando o problema é idêntico.

Mas situações que envolvem dados sempre podem apresentar mudanças.

Por exemplo, você pode aprender:

> "Como inserir no final."

E encontrar:

> "Como inserir no meio."

A diferença pode ser pequena no enunciado e enorme para quem decorou a solução.

Por isso:

> **Estude o princípio que permite construir o código, não apenas o código que foi apresentado.**

---

# 28. Como estudar algoritmos de ordenação

Ao estudar um algoritmo de ordenação, não olhe apenas para o código.

Analise uma sequência pequena:

```text
[5, 2, 4, 1, 3]
```

Acompanhe cada alteração:

```text
[5, 2, 4, 1, 3]

[2, 5, 4, 1, 3]

[2, 4, 5, 1, 3]

...
```

Pergunte:

* Qual elemento está sendo analisado?
* Com quem ele é comparado?
* Quando ocorre uma troca?
* Quantas vezes o algoritmo percorre os dados?
* O que acontece quando os dados já estão ordenados?
* O que acontece quando estão em ordem inversa?

Assim você começa a compreender o algoritmo como um processo.

---

# 29. Como estudar árvores

Árvores exigem bastante atenção porque possuem uma estrutura diferente das listas.

Comece sempre desenhando.

Por exemplo:

```text
             50
           /    \
         30      70
        /  \    /  \
      20   40  60   80
```

Depois pratique operações como:

* inserção;
* busca;
* percurso;
* remoção;
* identificação de folhas;
* identificação de nós internos;
* identificação de nós com um filho;
* altura da árvore;
* menor valor;
* maior valor.

Tente fazer os exercícios primeiro no papel.

Depois transforme o raciocínio em código.

---

# 30. O erro faz parte do aprendizado

Durante a disciplina, você provavelmente encontrará erros como:

```text
IndexError
AttributeError
TypeError
RecursionError
```

ou simplesmente:

```text
o programa executou, mas fez a coisa errada
```

O último caso pode ser ainda mais interessante.

Um erro de sintaxe normalmente faz o programa reclamar.

Um erro de lógica pode fazer o programa ficar em silêncio enquanto comete um pequeno desastre administrativo.

Por isso, aprender a **depurar** também faz parte da disciplina.

Quando algo der errado, pergunte:

1. Qual era o resultado esperado?
2. Qual resultado obtive?
3. Em que momento o comportamento começou a ficar diferente?
4. Quais valores as variáveis possuem naquele momento?
5. Qual condição ou operação poderia estar causando o problema?

---

# 31. O que significa realmente aprender Estrutura de Dados?

Ao final da disciplina, o objetivo não deve ser apenas conseguir escrever:

```python
class No:
    ...
```

ou:

```python
def buscar(...):
    ...
```

O objetivo é desenvolver a capacidade de olhar para um problema e pensar:

> **Como posso representar esses dados?**

Depois:

> **Quais operações preciso realizar?**

Depois:

> **Qual estrutura facilita essas operações?**

E finalmente:

> **Qual algoritmo resolve o problema de maneira adequada?**

Esse é o conhecimento que permanece mesmo quando a linguagem de programação muda.

---

# 32. Um exemplo de evolução do pensamento

Imagine o seguinte problema:

> Precisamos armazenar vários valores e encontrar rapidamente determinado valor.

Um programador iniciante pode pensar:

```text
"Vou colocar tudo em uma lista."
```

Um programador que está desenvolvendo pensamento algorítmico começa a fazer perguntas:

```text
Os dados estarão ordenados?
        ↓
Preciso pesquisar frequentemente?
        ↓
Preciso inserir frequentemente?
        ↓
Preciso remover elementos?
        ↓
Qual estrutura facilita essas operações?
        ↓
Qual algoritmo de busca posso utilizar?
        ↓
Qual será o custo dessa solução?
```

Perceba a mudança.

O foco deixa de ser apenas:

> **"Qual código eu escrevo?"**

E passa a ser:

> **"Qual solução faz sentido para este problema?"**

Essa mudança de pensamento é uma das principais contribuições da disciplina.

---

# 33. Checklist de aprendizagem

Antes de considerar um conteúdo realmente aprendido, tente verificar se consegue:

* [ ] Explicar o conceito com suas próprias palavras.
* [ ] Explicar para que a estrutura serve.
* [ ] Desenhar a estrutura.
* [ ] Identificar suas principais operações.
* [ ] Implementar a estrutura.
* [ ] Inserir elementos.
* [ ] Remover elementos.
* [ ] Pesquisar elementos.
* [ ] Percorrer a estrutura.
* [ ] Tratar estrutura vazia.
* [ ] Tratar estrutura com um elemento.
* [ ] Identificar casos especiais.
* [ ] Modificar um algoritmo existente.
* [ ] Resolver um problema diferente do exemplo.
* [ ] Explicar o próprio código.
* [ ] Identificar a complexidade aproximada do algoritmo.

Quanto mais itens você conseguir marcar, mais próximo estará de dominar o conteúdo.

---

# 34. Regra de ouro para a disciplina

Quando encontrar um exercício difícil, evite pensar imediatamente:

> "Eu não sei fazer."

Tente substituir por:

> "Qual parte do problema eu ainda não sei resolver?"

Depois divida o problema.

Por exemplo:

```text
Problema completo
      ↓
Entender os dados
      ↓
Definir a estrutura
      ↓
Resolver a inserção
      ↓
Resolver a busca
      ↓
Resolver a remoção
      ↓
Testar
      ↓
Analisar a eficiência
```

Problemas complexos ficam mais compreensíveis quando são divididos em problemas menores.

---

# 35. Conclusão

Estrutura de Dados existe porque **a forma como os dados são organizados influencia diretamente a maneira como podemos trabalhar com eles**.

A disciplina não tem como objetivo apenas ensinar listas, pilhas, filas ou árvores.

Essas estruturas são ferramentas para desenvolver uma habilidade maior:

> **pensar computacionalmente sobre problemas.**

Ao longo da disciplina, você será levado a perceber que existem várias maneiras de resolver um mesmo problema.

Algumas soluções são simples.

Outras são mais sofisticadas.

Algumas funcionam bem para poucos dados.

Outras continuam sendo eficientes quando a quantidade de dados cresce.

Por isso, aprender Estrutura de Dados significa desenvolver três perguntas fundamentais:

```text
1. COMO REPRESENTAR OS DADOS?

2. COMO RESOLVER O PROBLEMA?

3. QUAL É O CUSTO DA MINHA SOLUÇÃO?
```

Quando você consegue responder essas três perguntas, deixa de ser apenas alguém que escreve código e começa a desenvolver uma característica essencial de um bom programador:

> **a capacidade de construir soluções, compreender suas consequências e escolher estratégias adequadas para diferentes problemas.**

---

## Resumo da disciplina

**Disciplina:** Estrutura de Dados

**Carga Horária:** 60 horas

**Ementa:**

* Representação dos dados;
* Tipos abstratos de dados;
* Alocação dinâmica de memória;
* Listas e suas variantes;
* Recursividade;
* Busca em vetores;
* Pilhas;
* Filas;
* Árvores;
* Complexidade assintótica;
* Otimização.

### Avaliações

| Avaliação | Data            |
| --------- | --------------- |
| 1ª        | 29 de outubro   |
| 2ª        | 10 de dezembro  |
| 3ª        | 18 de fevereiro |

---

## Para estudar bem, lembre-se:

```text
NÃO APENAS LEIA
      ↓
ENTENDA
      ↓
DESENHE
      ↓
IMPLEMENTE
      ↓
TESTE
      ↓
ERRE
      ↓
CORRIJA
      ↓
EXPLIQUE
      ↓
MODIFIQUE
      ↓
RESOLVA UM NOVO PROBLEMA
```

**Estrutura de Dados não é uma disciplina para decorar códigos.**

É uma disciplina para aprender a **pensar sobre os códigos que você escreve**.
