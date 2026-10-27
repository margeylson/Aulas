# `print()` em Python

O comando `print()` é utilizado para **exibir informações na tela**.

Ele é um dos primeiros comandos que aprendemos em Python porque permite visualizar o resultado de um programa.

---

## 1. Exibindo uma mensagem

A forma mais simples de utilizar o `print()` é escrever uma mensagem entre aspas:

```python
print('Mensagem')
```

O resultado será:

```text
Mensagem
```

Podemos utilizar tanto **aspas simples** quanto **aspas duplas**:

```python
print('Mensagem')
print("Mensagem")
```

Os dois exemplos produzem o mesmo resultado.

---

## 2. Exibindo linhas de caracteres

O `print()` também pode ser utilizado para criar linhas e separadores na tela.

Por exemplo:

```python
print('==========================================')
```

Resultado:

```text
==========================================
```

Isso pode ser útil para organizar visualmente as informações apresentadas pelo programa.

---

## 3. Repetindo caracteres com `*`

Python possui uma característica interessante: podemos utilizar o operador `*` para repetir uma sequência de caracteres.

Por exemplo:

```python
print('='*50)
```

Nesse caso, o caractere `=` será repetido **50 vezes**.

O resultado será:

```text
==================================================
```

Observe que:

```python
'='*50
```

significa:

> Repita o caractere `=` 50 vezes.

Podemos utilizar o mesmo recurso com outros caracteres:

```python
print('-'*30)
print('*'*20)
print('#'*40)
```

Resultado:

```text
------------------------------
********************
########################################
```

---

## 4. Criando um menu

Podemos utilizar vários `print()` para construir uma interface simples para o nosso programa.

Por exemplo:

```python
print('|===========================================|')
print('|===========================================|')
print('| [1] - CADASTRAR                           |')
print('| [2] - EXIBIR                              |')
print('| [3] - PESQUISAR                           |')
print('| [4] - EDITAR                              |')
print('| [5] - EXCLUIR                             |')
print('| [0] - SAIR                                |')
print('|===========================================|')
```

O resultado será:

```text
|===========================================|
|===========================================|
| [1] - CADASTRAR                           |
| [2] - EXIBIR                              |
| [3] - PESQUISAR                           |
| [4] - EDITAR                              |
| [5] - EXCLUIR                             |
| [0] - SAIR                                |
|===========================================|
```

Aqui estamos utilizando o `print()` para criar uma pequena **interface textual**.

Ainda não estamos fazendo as opções funcionarem. O programa apenas está **exibindo o menu**.

---

## 5. Um exemplo completo

Podemos juntar os exemplos anteriores:

```python
print('Mensagem')

print('==========================================')
print('='*50)

print('|===========================================|')
print('|===========================================|')
print('| [1] - CADASTRAR                           |')
print('| [2] - EXIBIR                              |')
print('| [3] - PESQUISAR                           |')
print('| [4] - EDITAR                              |')
print('| [5] - EXCLUIR                             |')
print('| [0] - SAIR                                |')
print('|===========================================|')
```

O programa produzirá:

```text
Mensagem
==========================================
==================================================
|===========================================|
|===========================================|
| [1] - CADASTRAR                           |
| [2] - EXIBIR                              |
| [3] - PESQUISAR                           |
| [4] - EDITAR                              |
| [5] - EXCLUIR                             |
| [0] - SAIR                                |
|===========================================|
```

---

## 6. O que aprendemos?

Neste primeiro contato, vimos que o `print()` pode ser utilizado para:

- Exibir mensagens;
- Exibir números e outros valores;
- Criar linhas e separadores;
- Repetir caracteres utilizando `*`;
- Organizar informações na tela;
- Criar menus simples para programas.

O ponto principal é:

> **`print()` serve para mostrar informações na tela.**

Neste momento, nosso programa ainda não recebe informações do usuário nem toma decisões. Ele apenas **mostra informações**.

Esses recursos serão utilizados como base para construirmos programas cada vez mais completos.

---

## Exercício

Observe o menu abaixo:

```text
==========================================
|           SISTEMA ESCOLAR              |
==========================================
| [1] - CADASTRAR ALUNO                  |
| [2] - EXIBIR ALUNOS                    |
| [3] - PESQUISAR ALUNO                  |
| [0] - SAIR                             |
==========================================
```

### Desafio

Crie um programa em Python utilizando apenas `print()` que produza exatamente esse menu na tela.

Não é necessário fazer as opções funcionarem.

**Objetivo:** praticar a utilização do `print()` e a organização das informações exibidas pelo programa.
