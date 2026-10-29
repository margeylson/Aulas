# Estruturas Condicionais em Python

## 1. Introdução

Até aqui, aprendemos a exibir informações com `print()`, receber dados com `input()`, armazenar valores em variáveis e realizar operações matemáticas.

Agora vamos aprender a fazer nossos programas **tomarem decisões**.

Imagine algumas situações:

- Um sistema precisa verificar se uma pessoa tem idade suficiente para comprar um ingresso.
- Uma escola precisa verificar se um aluno foi aprovado, ficou de recuperação ou foi reprovado.
- Um sistema financeiro precisa liberar determinadas opções apenas para usuários autorizados.
- Um menu precisa executar uma ação de acordo com a opção escolhida pelo usuário.

Em todas essas situações, o programa precisa analisar uma condição antes de decidir o que fazer.

É para isso que utilizamos as **estruturas condicionais**.

---

## 2. A estrutura `if`

A palavra `if` significa "se".

Ela permite executar um trecho de código somente quando determinada condição é verdadeira.

Sua estrutura básica é:

```python
if condição:
    # Código executado quando a condição for verdadeira
```

Observe o exemplo:

```python
idade = 20

if idade >= 18:
    print('Maior de idade!')
```

Nesse programa, a condição verifica se `idade` é maior ou igual a `18`.

Como a variável `idade` possui o valor `20`, a condição é verdadeira e a mensagem é exibida.

### E se a condição for falsa?

Observe:

```python
idade = 15

if idade >= 18:
    print('Maior de idade!')
```

Nesse caso, nada será exibido, pois a condição é falsa e não existe outro bloco de código para executar.

Podemos representar essa ideia assim:

```text
          INÍCIO
             |
       Verificar idade
             |
       idade >= 18?
          /     \
        SIM      NÃO
         |        |
      Exibe     Não exibe
      mensagem  mensagem
         \        /
          Continua
```

O `if` permite que o programa escolha se determinado trecho será executado.

---

## 3. Operadores relacionais

Para construir condições, precisamos comparar valores.

Os operadores relacionais permitem realizar essas comparações.

| Operador | Significado | Exemplo |
|---|---|---|
| `==` | Igual a | `idade == 18` |
| `!=` | Diferente de | `idade != 18` |
| `>` | Maior que | `idade > 18` |
| `<` | Menor que | `idade < 18` |
| `>=` | Maior ou igual a | `idade >= 18` |
| `<=` | Menor ou igual a | `idade <= 18` |

O resultado de uma comparação é um valor lógico: `True` ou `False`.

Por exemplo:

```python
idade = 20

print(idade >= 18)
print(idade < 18)
```

Resultado:

```text
True
False
```

A primeira comparação é verdadeira, enquanto a segunda é falsa.

### Atenção: `=` não é o mesmo que `==`

Essa diferença é fundamental.

```python
idade = 20
```

O operador `=` atribui um valor à variável.

Já:

```python
idade == 20
```

O operador `==` verifica se o valor da variável é igual a `20`.

Em resumo:

- `=` atribui um valor.
- `==` compara dois valores.

Confundir esses operadores é um dos erros mais comuns no início da programação.

---

## 4. A importância da indentação

Em Python, a indentação determina quais instruções pertencem a uma estrutura condicional.

Observe:

```python
idade = 20

if idade >= 18:
    print('Pode entrar!')
    print('Acesso autorizado.')

print('Fim do programa.')
```

As duas primeiras mensagens estão indentadas. Portanto, elas pertencem ao bloco do `if`.

A última mensagem está fora do bloco e será executada independentemente da idade.

A saída será:

```text
Pode entrar!
Acesso autorizado.
Fim do programa.
```

Agora imagine que a idade seja `15`:

```text
Fim do programa.
```

Somente a mensagem que está fora do `if` será exibida.

**Regra importante:** após a condição, utilizamos `:` e indentamos as instruções que pertencem ao bloco.

No editor, é comum utilizar quatro espaços para cada nível de indentação.

---

## 5. A estrutura `if/else`

A palavra `else` significa "senão".

Ela permite definir o que acontece quando a condição do `if` é falsa.

Observe:

```python
idade = 16

if idade >= 18:
    print('Pode entrar!')
else:
    print('Não pode entrar!')
```

Como a idade é `16`, a condição é falsa. Portanto, o programa executa o bloco do `else`.

Resultado:

```text
Não pode entrar!
```

Podemos representar essa estrutura assim:

```text
          INÍCIO
             |
       Verificar idade
             |
       idade >= 18?
          /     \
        SIM      NÃO
         |        |
    Pode entrar  Não pode entrar
          \       /
           Continua
```

O `else` não possui uma condição própria. Ele representa o caminho alternativo quando a condição do `if` é falsa.

### 5.1 Exemplo: venda de ingresso

Vamos analisar o arquivo `venda_de_ingresso.py`:

```python
idade = int(input('Idade do comprador: '))

if idade > 17:
    print('Pode vender o ingresso!')
else:
    print('Não pode vender o ingresso!')
```

Primeiro, o programa solicita a idade do comprador.

Como o `input()` recebe inicialmente um texto, utilizamos `int()` para converter a informação em um número inteiro.

Depois, o programa verifica a condição:

```python
idade > 17
```

Se a idade for maior que `17`, a venda será autorizada pelo programa.

Caso contrário, será exibida a mensagem de que a venda não pode ser realizada.

Observe os resultados:

| Idade informada | Resultado |
|---:|---|
| 15 | Não pode vender o ingresso! |
| 17 | Não pode vender o ingresso! |
| 18 | Pode vender o ingresso! |
| 25 | Pode vender o ingresso! |

Nesse exemplo, `idade > 17` e `idade >= 18` produzem o mesmo resultado para idades inteiras.

Entretanto, se a regra fosse permitir a venda a partir dos 17 anos, a condição precisaria ser modificada.

**Atenção:** o programa implementa a regra que foi escrita. Cabe ao programador verificar se essa regra corresponde ao que o sistema realmente precisa fazer.

---

## 6. A estrutura `if/elif/else`

E quando precisamos analisar mais de duas possibilidades?

Imagine que uma escola utilize três classificações para a média de um aluno:

| Média | Situação |
|---|---|
| Menor que 2,5 | Reprovado |
| De 2,5 até menos de 7,0 | Final |
| De 7,0 até 10,0 | Aprovado |

Nesse caso, podemos utilizar `elif`, uma abreviação de *else if*.

A estrutura é:

```python
if primeira_condicao:
    # Primeiro caso
elif segunda_condicao:
    # Segundo caso
else:
    # Demais casos
```

O Python verifica as condições em ordem. Quando encontra uma condição verdadeira, executa o bloco correspondente e ignora os demais blocos daquela estrutura.

### 6.1 Exemplo: situação do aluno

Vamos analisar o arquivo `media.py`:

```python
media = float(input('Digite a média: '))

if media < 2.5:
    print('REPROVADO!')
elif media < 7.0:
    print('FINAL')
else:
    print('APROVADO')
```

Primeiro, o programa recebe a média e a converte para `float`, permitindo trabalhar com valores decimais.

Em seguida, analisa as condições.

**Primeira condição:**

```python
if media < 2.5:
```

Se a média for menor que `2.5`, o resultado será `REPROVADO!`.

**Segunda condição:**

```python
elif media < 7.0:
```

Essa condição somente será verificada se a primeira for falsa.

Portanto, nesse ponto, sabemos que a média é maior ou igual a `2.5`. Se também for menor que `7.0`, o resultado será `FINAL`.

**Último caso:**

```python
else:
    print('APROVADO')
```

Se nenhuma das condições anteriores for verdadeira, o programa executará o `else`.

### 6.2 Testando os limites

| Média | Resultado |
|---:|---|
| 1,5 | REPROVADO! |
| 2,4 | REPROVADO! |
| 2,5 | FINAL |
| 6,9 | FINAL |
| 7,0 | APROVADO |
| 9,5 | APROVADO |

Observe que a ordem das condições é importante.

O programa não precisa verificar novamente se a média é maior ou igual a `2.5` no `elif`, pois esse caso já foi excluído pela primeira condição.

### Um cuidado importante

O exemplo original não verifica se a média está dentro do intervalo permitido de `0` a `10`.

Assim, uma média negativa seria classificada como reprovada e uma média superior a `10` seria classificada como aprovada.

Em um sistema real, podemos precisar validar esses valores antes de classificar o aluno.

---

## 7. A ordem das condições faz diferença

Observe este exemplo:

```python
media = 8.0

if media >= 2.5:
    print('FINAL')
elif media >= 7.0:
    print('APROVADO')
```

O resultado será:

```text
FINAL
```

Mas por quê?

A primeira condição, `media >= 2.5`, já é verdadeira para uma média de `8.0`.

Como o Python executa o primeiro bloco verdadeiro, a segunda condição nunca é verificada.

Podemos corrigir o problema organizando as condições:

```python
media = 8.0

if media >= 7.0:
    print('APROVADO')
elif media >= 2.5:
    print('FINAL')
else:
    print('REPROVADO')
```

Agora o resultado será:

```text
APROVADO
```

**Lição importante:** ao trabalhar com `if/elif/else`, devemos organizar as condições de forma que os casos mais específicos ou prioritários sejam analisados adequadamente.

---

## 8. Condicionais com várias faixas de valores

As estruturas condicionais também podem classificar valores em diferentes faixas.

Imagine um sistema de vendas que determina uma comissão de acordo com o valor vendido.

O arquivo `c05_comissao_vendas.py` apresenta a seguinte lógica:

```python
vendas = int(input('Valor da venda: '))

if vendas < 1000:
    print('Comissão de 2%')

elif vendas < 3000:
    print('Comissão de 4%')

elif vendas < 5000:
    print('Comissão de 6%')

elif vendas < 7000:
    print('Comissão de 8%')

else:
    print('Comissão de 12%')
```

Vamos entender o funcionamento.

| Valor das vendas | Comissão apresentada |
|---|---:|
| Menor que 1.000 | 2% |
| De 1.000 até menos de 3.000 | 4% |
| De 3.000 até menos de 5.000 | 6% |
| De 5.000 até menos de 7.000 | 8% |
| A partir de 7.000 | 12% |

O programa verifica as faixas na ordem em que foram escritas.

Por exemplo, se o usuário informar `4000`, teremos:

1. `4000 < 1000`? Não.
2. `4000 < 3000`? Não.
3. `4000 < 5000`? Sim.
4. O programa exibe `Comissão de 6%` e encerra essa estrutura condicional.

Não é necessário verificar as condições seguintes.

### Atenção à especificação

No comentário original do arquivo, a tabela apresenta os percentuais de 2%, 4%, 6% e 12%, sem mencionar a faixa de 8%.

Entretanto, o código inclui a faixa de 8% para vendas de 5.000 até menos de 7.000.

Isso demonstra uma prática importante na programação: **a regra descrita e o código precisam estar de acordo**.

Se a regra desejada fosse utilizar somente os quatro percentuais do comentário original, o código deveria ser ajustado:

```python
vendas = int(input('Valor da venda: '))

if vendas < 1000:
    print('Comissão de 2%')
elif vendas < 3000:
    print('Comissão de 4%')
elif vendas < 5000:
    print('Comissão de 6%')
else:
    print('Comissão de 12%')
```

Antes de programar, é importante esclarecer os limites das faixas e os percentuais aplicáveis a cada uma delas.

---

## 9. Utilizando condicionais para controlar um menu

Um menu apresenta opções para que o usuário escolha o que deseja fazer.

Observe o arquivo `c05_menu.py`:

```python
print('MEU SISTEMA')
print('1- Cadastrar')
print('2- Exibir')
print('3- Editar')
print('0- Sair')

op = int(input('> '))

if op == 1:
    print('CADASTRANDO NOVO CLIENTE')

elif op == 2:
    print('EXIBINDO RELATÓRIO DE CLIENTES')

elif op == 3:
    print('EDITANDO CLIENTE')

elif op == 0:
    print('SAINDO')

else:
    print('OPÇÃO INVÁLIDA!')
```

O programa apresenta quatro opções e solicita que o usuário informe uma delas.

A variável `op` armazena a opção escolhida.

Depois, o programa verifica o valor informado:

- Se `op == 1`, apresenta a mensagem de cadastro.
- Se `op == 2`, apresenta a mensagem de exibição.
- Se `op == 3`, apresenta a mensagem de edição.
- Se `op == 0`, apresenta a mensagem de saída.
- Se nenhuma dessas condições for verdadeira, apresenta uma mensagem de opção inválida.

### Exemplo de execução

```text
MEU SISTEMA
1- Cadastrar
2- Exibir
3- Editar
0- Sair
> 2
EXIBINDO RELATÓRIO DE CLIENTES
```

Se o usuário informar `5`, teremos:

```text
> 5
OPÇÃO INVÁLIDA!
```

Neste exemplo, as opções ainda não realizam operações reais. Elas apenas exibem mensagens. O objetivo é compreender como uma escolha pode direcionar a execução do programa.

---

## 10. Condicionais e autorização de acesso

Podemos utilizar condições para exibir opções diferentes de acordo com uma informação fornecida pelo usuário.

Observe o arquivo `condicionais.py`:

```python
senha = int(input('Digite a senha: '))

print('[1] - Vender Ingresso')
print('[2] - Cancelar Ingresso')

if senha == 1020:
    print('[3] - Visualizar financeiro')
    print('[4] - Transferir recursos')

print('[0] - Sair do Sistema')
```

Nesse programa, as opções de venda e cancelamento são exibidas para todos os usuários.

Entretanto, as opções financeiras somente aparecem quando a senha informada é igual a `1020`.

Observe que as duas mensagens estão indentadas:

```python
if senha == 1020:
    print('[3] - Visualizar financeiro')
    print('[4] - Transferir recursos')
```

Por isso, ambas pertencem ao mesmo bloco condicional.

A última mensagem:

```python
print('[0] - Sair do Sistema')
```

está fora do `if`. Portanto, ela sempre será exibida.

### O que acontece em cada caso?

Se a senha for `1020`:

```text
[1] - Vender Ingresso
[2] - Cancelar Ingresso
[3] - Visualizar financeiro
[4] - Transferir recursos
[0] - Sair do Sistema
```

Se a senha for diferente:

```text
[1] - Vender Ingresso
[2] - Cancelar Ingresso
[0] - Sair do Sistema
```

Esse exemplo permite perceber que as condicionais podem controlar não apenas mensagens isoladas, mas também diferentes partes de uma interface.

**Observação de segurança:** esconder opções na tela não é suficiente para proteger um sistema real. As operações financeiras também precisariam verificar a autorização antes de serem executadas.

---

## 11. Operadores lógicos

Além de comparar valores individualmente, podemos combinar condições.

Para isso, utilizamos operadores lógicos.

| Operador | Significado |
|---|---|
| `and` | E |
| `or` | OU |
| `not` | NÃO |

### 11.1 Operador `and`

O `and` exige que as duas condições sejam verdadeiras.

```python
idade = 20
possui_ingresso = True

if idade >= 18 and possui_ingresso:
    print('Entrada autorizada!')
else:
    print('Entrada não autorizada!')
```

Para que a mensagem de autorização seja exibida, a idade precisa ser maior ou igual a `18` e a pessoa precisa possuir ingresso.

Se uma das condições for falsa, o resultado da expressão será falso.

### 11.2 Operador `or`

O `or` exige que pelo menos uma das condições seja verdadeira.

```python
dia = 'sábado'

if dia == 'sábado' or dia == 'domingo':
    print('É fim de semana!')
else:
    print('É dia útil!')
```

Se o dia for sábado ou domingo, a mensagem de fim de semana será exibida.

### 11.3 Operador `not`

O `not` inverte o resultado lógico de uma expressão.

```python
esta_chovendo = False

if not esta_chovendo:
    print('Podemos sair!')
```

Como `esta_chovendo` é falso, `not esta_chovendo` será verdadeiro.

Esses operadores permitem construir regras mais completas, combinando diferentes informações.

---

## 12. Condições dentro de condições

Podemos colocar um `if` dentro de outro `if`. Essa estrutura é chamada de **condicional aninhada**.

Por exemplo:

```python
idade = int(input('Digite sua idade: '))
possui_autorizacao = input('Possui autorização? (s/n): ')

if idade >= 18:
    print('Entrada permitida!')
else:
    if possui_autorizacao == 's':
        print('Verifique as regras de autorização.')
    else:
        print('Entrada não permitida!')
```

Nesse exemplo, se a pessoa tiver menos de 18 anos, o programa verifica uma segunda condição.

Observe que o segundo `if` pertence ao bloco do primeiro `else`, pois está mais indentado.

Condicionais aninhadas são úteis quando uma decisão depende do resultado de outra. Entretanto, quando muitas condições são necessárias, vale avaliar se a lógica pode ser organizada de forma mais simples.

---

## 13. Validando valores informados pelo usuário

Nos exemplos anteriores, utilizamos conversões como:

```python
idade = int(input('Digite sua idade: '))
```

Essa forma funciona quando o usuário digita um número inteiro válido.

Porém, se ele digitar `vinte`, por exemplo, a conversão para `int` falhará e o programa apresentará um erro.

Também precisamos considerar valores fora dos limites esperados.

Por exemplo, uma média escolar normalmente deve estar entre `0` e `10`.

Podemos verificar esse intervalo:

```python
media = float(input('Digite a média: '))

if media < 0 or media > 10:
    print('Média inválida!')
elif media < 2.5:
    print('REPROVADO!')
elif media < 7.0:
    print('FINAL')
else:
    print('APROVADO')
```

A primeira condição identifica valores fora do intervalo permitido.

Se ela for falsa, sabemos que a média está entre `0` e `10`, inclusive. Em seguida, podemos classificar a situação do aluno.

Esse exemplo ainda não trata entradas que não sejam numéricas, mas demonstra como as condicionais podem ser utilizadas para validar dados.

---

## 14. Erros comuns ao utilizar condicionais

### Erro 1: esquecer os dois-pontos

Incorreto:

```python
if idade >= 18
    print('Maior de idade!')
```

Correto:

```python
if idade >= 18:
    print('Maior de idade!')
```

### Erro 2: esquecer a indentação

Incorreto:

```python
if idade >= 18:
print('Maior de idade!')
```

Correto:

```python
if idade >= 18:
    print('Maior de idade!')
```

### Erro 3: confundir atribuição e comparação

Incorreto:

```python
if idade = 18:
    print('Tem 18 anos!')
```

Correto:

```python
if idade == 18:
    print('Tem 18 anos!')
```

### Erro 4: utilizar condições que se sobrepõem de maneira inadequada

Observe:

```python
nota = 8

if nota >= 5:
    print('Aprovado')

elif nota >= 7:
    print('Aprovado com destaque')
```

A segunda condição nunca será alcançada para notas maiores ou iguais a `7`, pois a primeira já será verdadeira.

Uma organização melhor seria:

```python
nota = 8

if nota >= 7:
    print('Aprovado com destaque')
elif nota >= 5:
    print('Aprovado')
else:
    print('Reprovado')
```

### Erro 5: esquecer que o `else` corresponde ao bloco condicional

Um `else` não possui uma condição própria e precisa estar associado a um `if` ou `elif` no mesmo nível de indentação.

Além disso, em uma mesma estrutura `if/elif/else`, apenas o primeiro bloco cuja condição for verdadeira será executado.

---

## 15. Exercícios para praticar

### Exercício 1: número positivo

Leia um número inteiro e informe se ele é positivo.

Considere que zero não é positivo.

### Exercício 2: par ou ímpar

Leia um número inteiro e informe se ele é par ou ímpar.

Dica: o operador `%` fornece o resto de uma divisão.

### Exercício 3: aprovação escolar

Leia a média de um aluno e apresente uma das mensagens:

- Menor que `5`: Reprovado.
- De `5` até menos de `7`: Recuperação.
- De `7` até `10`: Aprovado.

Valores fora do intervalo de `0` a `10` devem ser considerados inválidos.

### Exercício 4: maior número

Leia dois números e informe qual deles é o maior. Se forem iguais, informe que possuem o mesmo valor.

### Exercício 5: menu de operações

Crie um menu com as seguintes opções:

```text
SISTEMA DE CADASTRO

1 - Cadastrar
2 - Consultar
3 - Atualizar
0 - Sair
```

Leia a opção escolhida e apresente uma mensagem correspondente.

Se a opção não existir, apresente `OPÇÃO INVÁLIDA!`.

### Exercício 6: comissão de vendas

Leia o valor de uma venda e apresente a comissão de acordo com as regras:

| Valor da venda | Comissão |
|---|---:|
| Menor que R$ 1.000 | 2% |
| De R$ 1.000 até menos de R$ 3.000 | 4% |
| De R$ 3.000 até menos de R$ 5.000 | 6% |
| A partir de R$ 5.000 | 12% |

Neste exercício, basta apresentar o percentual. Não é necessário calcular o valor da comissão.

### Exercício 7: acesso ao sistema

Leia uma senha numérica.

Se a senha for igual a `1020`, apresente:

```text
Acesso autorizado!
```

Caso contrário, apresente:

```text
Acesso negado!
```

---

## 16. Resumo

As estruturas condicionais permitem que um programa execute diferentes instruções de acordo com determinadas condições.

| Estrutura | Utilização |
|---|---|
| `if` | Executa um bloco quando uma condição é verdadeira. |
| `else` | Define o caminho alternativo quando a condição anterior é falsa. |
| `elif` | Permite testar outra condição quando as anteriores são falsas. |

Também aprendemos a utilizar:

- Operadores relacionais para comparar valores;
- Operadores lógicos para combinar condições;
- Indentação para organizar os blocos;
- Condicionais aninhadas para decisões dependentes;
- Validações para identificar valores fora dos limites esperados.

A ideia central é:

**Receber informações → Avaliar condições → Executar o bloco adequado.**

As estruturas condicionais são uma das bases da lógica de programação. Com elas, deixamos de escrever programas que apenas executam uma sequência fixa de instruções e começamos a criar programas capazes de reagir a diferentes situações.
