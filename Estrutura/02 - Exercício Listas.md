# Exercício Lista

O objetivo do exercício é treinar o uso de listas, revisar o conteúdo de busca linear e embasar o conteúdo de ordenação de dados.


``` text
Sistema que relaize o cadastro de atletas, guardando seu nome e sua altura em duas listas.
Listas:
Nomes = []
Alturas = []

1. Guardar os dados dos atletas através da função cadastrar(nome, altura).
2. Criar a função exibir_atletas() para mostrar os dados cadastrados.
3. Encontrar um atleta pelo seu nome na função buscar(nome).
4. Achar o atleta mais alto
5. Achar o atleta mai baixo

```

## Solução

```python
Nomes = []
Alturas = []

def cadasrar(nome, altura):
   Nomes.append(nome) 
   Alturas.append(altura)
   return f'{nome} cadastrado co sucesso!'

def exibir_atletas():
    for p in range(len(Nomes)):
        print(f'Nome: {Nomes[p]}')
        print(f'Altura: {Alturas[p]}')
        print('-'*50)

def buscar(nome):
    encontrado = False

    for p in Nomes:
        if p == nome:
            posicao = Nomes.index(p)
            print(f'Dado encontrado na posição: {posicao}')
            print(f'Nome: {Nomes[posicao]}')
            print(f'Altura: {Altura[posicao]}')
            return

# PROGRAMA PRINCIPAL =====================================
while True:
    print('1. CADASTRAR')
    print('2. EXIBIR')
    print('3. BUSCAR')
    print('0. SAIR')

    op = int(input('--> '))

    if op == 1:
        nome = input('Nome do atleta: ')
        altura = int(input('Altura (cm): '))
        cadasrar(nome, altura)
    
    elif op == 2:
        exibir_atletas()
    
    elif op == 3:
        nome = input('Buscar pelo atleta: ')
        buscar(nome)

```