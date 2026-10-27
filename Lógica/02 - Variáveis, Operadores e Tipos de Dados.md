# Variáveis, Operadores e Tipos de Dados

Neste momento, já aprendemos a utilizar o `print()` para exibir informações na tela.

Agora vamos dar um passo importante: **guardar e manipular informações dentro do programa**.

Para isso, vamos conhecer:

- Variáveis;
- Entrada de dados com `input()`;
- Operadores matemáticos;
- Tipos de dados;
- Conversão de tipos (*casting*).

---

# 1. Variáveis

Uma **variável** é um espaço utilizado pelo programa para **guardar uma informação**.

Podemos imaginar uma variável como uma "caixa" que possui um nome e guarda algum valor.

Por exemplo:

```python
idade = 20
```

Nesse caso:

- `idade` é o nome da variável;
- `20` é o valor armazenado.

Podemos posteriormente utilizar esse valor:

```python
idade = 20

print(idade)
```

Resultado:

```text
20
```

---

## 1.1 Criando uma variável

Para criar uma variável, utilizamos o sinal de `=`.

```python
nome = 'Maria'
idade = 20
telefone = '99999-9999'
```

Podemos então utilizar essas informações:

```python
print(nome)
print(idade)
print(telefone)
```

Uma variável pode guardar diferentes tipos de informação.

---

# 2. Regras para nomes de variáveis

Ao criar uma variável, precisamos seguir algumas regras da linguagem Python.

## 2.1 Não podemos utilizar espaços

Não podemos fazer:

```python
valor de venda = 100
```

O Python interpretaria isso de forma incorreta.

Podemos utilizar o caractere `_` para separar as palavras:

```python
valor_de_venda = 100
```

---

## 2.2 Não podemos começar o nome com números

Não podemos fazer:

```python
1nome = 'Maria'
```

Mas podemos utilizar números depois do primeiro caractere:

```python
nome1 = 'Maria'
```

ou:

```python
nome1_cliente = 'Maria'
```

---

## 2.3 Caracteres especiais devem ser evitados

Não devemos utilizar caracteres especiais na criação dos nomes:

```python
#$%ç~
```

Por exemplo:

```python
nome@cliente = 'Maria'
```

está incorreto.

Utilizamos letras, números e `_`.

---

## 2.4 Devemos escolher nomes que representem o conteúdo

O nome da variável deve ajudar a entender **qual informação está sendo armazenada**.

Evite:

```python
x = 'Maria'
y = 25
z = '99999-9999'
```

Prefira:

```python
nome = 'Maria'
idade = 25
telefone = '99999-9999'
```

Os nomes tornam o programa muito mais fácil de entender.

---

## 2.5 Utilize nomes em minúsculas

Python permite nomes escritos em maiúsculas, mas, por convenção, normalmente utilizamos letras minúsculas para variáveis.

Por exemplo:

```python
nome = 'Maria'
idade = 20
```

Em vez de:

```python
NOME = 'Maria'
IDADE = 20
```

Também podemos utilizar mais de uma palavra:

```python
nome_cliente = 'Maria'
idade_cliente = 20
```

Ou, utilizando o padrão `camelCase`:

```python
nomeCliente = 'Maria'
idadeCliente = 20
```

Neste curso, podemos adotar o padrão com `_`:

```python
nome_cliente
idade_cliente
valor_produto
```

---

# 3. Atribuindo valores

Podemos colocar diretamente um valor dentro de uma variável:

```python
idade = 20
```

Também podemos obter um valor fornecido pelo usuário.

Para isso, utilizamos o comando `input()`.

```python
nome = input('Digite seu nome: ')
```

Nesse caso, o programa apresenta a mensagem:

```text
Digite seu nome:
```

O usuário pode digitar:

```text
Maria
```

E o valor digitado será armazenado na variável `nome`.

Podemos utilizar essa informação posteriormente:

```python
nome = input('Digite seu nome: ')

print(f'Seu nome é {nome}!')
```

Se o usuário digitar `Maria`, teremos:

```text
Digite seu nome: Maria
Seu nome é Maria!
```

---

# 4. `input()` e entrada de dados

O `input()` permite que o programa **receba uma informação do usuário**.

Por exemplo:

```python
nome = input('Digite seu nome: ')
```

Podemos fazer isso com várias informações:

```python
nome = input('Digite seu nome: ')
idade = input('Digite sua idade: ')
cidade = input('Digite sua cidade: ')
```

Agora temos três variáveis:

```text
nome
idade
cidade
```

Cada uma guarda uma informação fornecida pelo usuário.

---

# 5. Uma informação por variável

É uma boa prática utilizar variáveis para guardar as informações que serão utilizadas pelo programa.

Por exemplo:

```python
nome = input('Digite seu nome: ')
idade = input('Digite sua idade: ')
```

Depois podemos utilizar essas informações:

```python
print(f'Nome: {nome}')
print(f'Idade: {idade}')
```

A ideia é simples:

> **Recebemos uma informação, guardamos em uma variável e podemos utilizá-la posteriormente.**

---

# 6. Operadores matemáticos

Os operadores matemáticos são utilizados para realizar operações com números.

Os principais operadores que utilizaremos inicialmente são:

| Operador | Operação |
|---|---|
| `+` | Soma |
| `-` | Subtração |
| `*` | Multiplicação |
| `/` | Divisão |

---

## 6.1 Soma

Utilizamos `+` para realizar uma soma.

```python
n1 = 60
n2 = 2

resultado = n1 + n2

print(f'{n1} + {n2} = {resultado}')
```

Resultado:

```text
60 + 2 = 62
```

---

## 6.2 Subtração

Utilizamos `-` para realizar uma subtração.

```python
n1 = 60
n2 = 2

resultado = n1 - n2

print(f'{n1} - {n2} = {resultado}')
```

Resultado:

```text
60 - 2 = 58
```

---

## 6.3 Multiplicação

Utilizamos `*` para realizar uma multiplicação.

```python
n1 = 60
n2 = 2

resultado = n1 * n2

print(f'{n1} * {n2} = {resultado}')
```

Resultado:

```text
60 * 2 = 120
```

---

## 6.4 Divisão

Utilizamos `/` para realizar uma divisão.

```python
n1 = 60
n2 = 2

resultado = n1 / n2

print(f'{n1} / {n2} = {resultado}')
```

Resultado:

```text
60 / 2 = 30.0
```

Observe que o resultado aparece como `30.0`.

Isso acontece porque o operador `/` produz um resultado do tipo `float`, mesmo quando a divisão é exata.

---

# 7. Tipos de dados

Uma variável pode guardar diferentes tipos de informação.

Os principais tipos que utilizaremos inicialmente são:

| Tipo | Utilização | Exemplos |
|---|---|---|
| `str` | Textos | `'Maria'`, `'Python'` |
| `int` | Números inteiros | `5`, `8`, `10` |
| `float` | Números com casas decimais | `5.8`, `8.7`, `10.45` |

---

## 7.1 String (`str`)

Uma `string` representa um **texto**.

```python
nome = 'Maria'
cidade = 'Valença'
```

Podemos também utilizar aspas duplas:

```python
nome = "Maria"
```

Nos dois casos estamos trabalhando com texto.

---

## 7.2 Inteiro (`int`)

O tipo `int` representa **números inteiros**, sem casas decimais.

Exemplos:

```python
idade = 20
quantidade = 10
ano = 2029
```

---

## 7.3 Decimal (`float`)

O tipo `float` representa números que possuem casas decimais.

Exemplos:

```python
altura = 1.75
preco = 19.90
temperatura = 32.5
```

---

## 7.4 E o `double`?

Em algumas linguagens de programação existe um tipo chamado `double`.

Em Python, porém, não utilizamos `double` como um tipo separado.

Para números de ponto flutuante, utilizamos:

```python
float
```

Portanto, neste momento, podemos trabalhar principalmente com:

```text
str   → textos
int   → números inteiros
float → números decimais
```

---

# 8. O tipo de uma variável

Podemos descobrir o tipo de uma informação utilizando `type()`.

Por exemplo:

```python
nome = 'Maria'
idade = 20
altura = 1.75

print(type(nome))
print(type(idade))
print(type(altura))
```

O resultado será semelhante a:

```text
<class 'str'>
<class 'int'>
<class 'float'>
```

Isso permite verificar qual tipo de dado está armazenado em uma variável.

---

# 9. Atenção com o `input()`

Existe uma característica muito importante do `input()`:

> **Toda informação recebida por `input()` é inicialmente tratada como `str`.**

Observe:

```python
idade = input('Digite sua idade: ')
```

Mesmo que o usuário digite:

```text
20
```

a informação recebida será uma `string`.

Podemos verificar:

```python
idade = input('Digite sua idade: ')

print(type(idade))
```

Resultado:

```text
<class 'str'>
```

Isso pode causar um problema quando queremos realizar operações matemáticas.

---

# 10. Um problema com números recebidos pelo `input()`

Observe o código:

```python
val1 = input('Número 1: ')
val2 = input('Número 2: ')

resultado = val1 + val2

print(resultado)
```

Imagine que o usuário informe:

```text
Número 1: 10
Número 2: 20
```

Podemos esperar:

```text
30
```

Mas o resultado será:

```text
1020
```

Por quê?

Porque os valores recebidos pelo `input()` são textos.

Nesse caso, o operador `+` está **juntando os textos**, em vez de realizar uma soma matemática.

---

# 11. Conversão de tipos (*casting*)

Quando precisamos transformar um valor de um tipo para outro, podemos realizar uma **conversão de tipos**, também conhecida como *casting*.

A ideia geral é:

```text
tipo_que_quero(valor_que_tenho)
```

Por exemplo:

```python
int('20')
```

transforma o texto `'20'` em um número inteiro.

Podemos utilizar isso diretamente com `input()`:

```python
idade = int(input('Digite sua idade: '))
```

Nesse caso:

1. `input()` recebe a informação do usuário;
2. A informação é recebida como `str`;
3. `int()` converte o valor para `int`;
4. O resultado é armazenado na variável `idade`.

---

# 12. Fazendo a soma corretamente

Agora podemos corrigir o exemplo anterior:

```python
val1 = int(input('Número 1: '))
val2 = int(input('Número 2: '))

resultado = val1 + val2

print(resultado)
```

Se o usuário informar:

```text
Número 1: 10
Número 2: 20
```

teremos:

```text
30
```

Agora a soma é matemática porque os valores foram convertidos para `int`.

---

# 13. Outros tipos de conversão

Podemos converter valores para outros tipos.

Por exemplo:

### Para inteiro

```python
int('10')
```

### Para decimal

```python
float('10.5')
```

### Para texto

```python
str(10)
```

Assim, podemos transformar informações de acordo com a necessidade do programa.

---

# 14. Exemplo completo

Agora podemos juntar os conceitos apresentados.

Vamos criar um programa que recebe o nome e a idade do usuário:

```python
nome = input('Digite seu nome: ')
idade = int(input('Digite sua idade: '))

print(f'Olá, {nome}!')
print(f'Você tem {idade} anos.')
```

Se o usuário informar:

```text
Digite seu nome: Maria
Digite sua idade: 20
```

teremos:

```text
Olá, Maria!
Você tem 20 anos.
```

Observe que utilizamos:

- `input()` para receber informações;
- variáveis para armazenar as informações;
- `int()` para converter a idade;
- `print()` para apresentar o resultado;
- `f'...'` para inserir os valores das variáveis dentro do texto.

---

# 15. Exercício resolvido

## Problema

Leia o ano de nascimento do usuário e calcule quantos anos a pessoa terá em **31 de dezembro de 2029**.

Além disso, leia o nome da pessoa e apresente uma mensagem informando sua idade.

---

## Resolução

```python
nome = input('Digite seu nome: ')
ano_nascimento = int(input('Ano de nascimento: '))

idade = 2029 - ano_nascimento

print(f'Olá, {nome}! Sua idade em 2029 será {idade} anos.')
```

### Exemplo de execução

```text
Digite seu nome: Maria
Ano de nascimento: 2005

Olá, Maria! Sua idade em 2029 será 24 anos.
```

---

# 16. O que aconteceu nesse programa?

Vamos analisar cada parte.

### 1. Recebemos o nome

```python
nome = input('Digite seu nome: ')
```

O usuário fornece o nome e ele é armazenado na variável `nome`.

---

### 2. Recebemos o ano de nascimento

```python
ano_nascimento = int(input('Ano de nascimento: '))
```

Aqui temos duas operações:

```python
input('Ano de nascimento: ')
```

recebe o valor como texto.

Depois:

```python
int(...)
```

converte esse texto para um número inteiro.

Finalmente, o valor é armazenado em:

```python
ano_nascimento
```

---

### 3. Calculamos a idade

```python
idade = 2029 - ano_nascimento
```

O programa subtrai o ano de nascimento de 2029.

Por exemplo:

```text
2029 - 2005 = 24
```

O resultado é armazenado na variável:

```python
idade
```

---

### 4. Apresentamos o resultado

```python
print(f'Olá, {nome}! Sua idade em 2029 será {idade} anos.')
```

O `print()` apresenta a mensagem na tela e as variáveis são inseridas no texto por meio da **f-string**.

---

# 17. Resumo

Neste segundo momento, aprendemos que:

### Variáveis

Servem para armazenar informações.

```python
nome = 'Maria'
idade = 20
```

### Entrada de dados

Utilizamos `input()` para receber informações do usuário.

```python
nome = input('Digite seu nome: ')
```

### Operadores matemáticos

```text
+ → soma
- → subtração
* → multiplicação
/ → divisão
```

### Tipos de dados

```text
str   → texto
int   → número inteiro
float → número decimal
```

### Conversão de tipos

Podemos converter um valor utilizando funções como:

```python
int()
float()
str()
```

### Uma regra importante

> **O `input()` recebe inicialmente a informação como `str`.**

Por isso, quando esperamos receber um número para realizar cálculos, normalmente precisamos fazer a conversão:

```python
idade = int(input('Digite sua idade: '))
```

---

# 18. A ideia central

Podemos resumir o que aprendemos até aqui em um pequeno fluxo:

```text
           USUÁRIO
              ↓
           input()
              ↓
        INFORMAÇÃO
              ↓
           VARIÁVEL
              ↓
     PROCESSAMENTO
              ↓
           print()
              ↓
             TELA
```

Ou, em outras palavras:

> **Receber → Guardar → Processar → Exibir**

Esse ciclo será a base para construirmos programas cada vez mais completos.
