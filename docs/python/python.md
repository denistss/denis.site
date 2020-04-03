#Gráficos em Python
##Importando Bibliotecas Python 

```python
%matplotlib inline --> #Inicia a ferramenta do python;

import pandas as pd --> #Importa a biblioteca pandas e dá o apelido 'pd';

import matplotlib.pyplot as plt --> #Importa a biblioteca matplotlib e dá um apelido 'plt';

import seaborn as sns ---> #Importa a biblioteca Seaborn e dá um apelido 'sns';

plt.style.use('ggplot') ---> #Configura a plotagem do gráfico;
```

##Códigos de Criação e Manipulação de Gráficos
```python
#Criar uma variável para inserir o Dataset(base de dados para análise);
nome_variavel = pd.read_csv('nome_arquivo.csv')

#Visualizar a quantidade de linhas da tabela de dados do Dataset;
nome_variavel.head(numero_linhas)

#Visualizar informações das colunas;
nome_variavel.describe()

#Visualizar tipo de dado de cada coluna;
nome_variavel.dtypes

#Visualizar quantidades de linhas e colunas do Dataset;
nome_variavel.shape

#Visualizar quantidades de uma ou várias colunas;
nome_variavel['Nome_coluna'].value_counts()

#Plotar um gráfico simples de coluna e valores usando a biblioteca pandas/matplotlib, usando o código de plotagem '.plot()';
nome_variavel['Nome_coluna'].value_counts().plot

#Plotar um gráfico visualmente elaborado em uma linha de código;
nome_variavel['Nome_coluna'].value_counts().head(10).plot(kind='bar', figsize=(11,5), grid=False, rot=0, color='blue')

kind
#Informa o tipo de gráfico a ser criado, neste caso tipo barra (bar);

figsize
#Informa o tamanho que deseja criar o gráfico, necessario informar em Tupla (0,0), entre parenteses;

grid
#Informa se deseja colocar linhas de grade na plotagem, neste caso não será adicionado, então fica False;

rot
#Informa o grau de rotação que os dados do eixo X vão ficar, neste caso será reto sem inclinação, valor 0;

color
#Informa a cor que deseja colocar no gráfico, neste caso azul (blue);

#Plotar um gráfico com Títulos e legendas;
plt.title('Título do Gráfico')
plt.xlabel('Legenda do Eixo X')
plt.ylabel('Legenda do Eixo Y')
plt.show() #Plota o gráfico
```
#Manipulando loops em *Python*

##loops aninhados
```python
for i in range(0,5):
    for a in range(0,5):
        print(a)
```
##Operando valores em lista usando for
```python
listab = [32,53,85,10,15,17,19]
soma = 0
for i in listab:
    double_i = i * 2
    soma += double_i
print(soma)
```
##loops em listas dentro de listas
```python
listaa = [[1,2,3],[10,15,14],[10.1,8.7,2.3]]
for valor in lista:
    print(valor)
```
##Contar a quantidade de itens de uma lista
```python
lista1 = [5,10,13,17]
count = 0
for item in lista1:
    count += 1  
print(count)
```
##Contar a quantidade de colunas de um item da lista
```python
lista2 = [[1,2,3],[3,3,5],[5,6,7]]
primeiro_item = lista2[0]
count = 0
for colunas in primeiro_item:
    count += 1
print(count)
```
##Pesquisando em listas
```python
lista3 = [5,6,7,8,9,10]
for item in lista3:
    if item == 5:
        print("Número 5 encontrado!")
```
##Usando *while* para contar de 0 a 5
```python
count = 0
while count < 6:
    print(count)
    count += 1
```
##Usando *else* para dar stop de loop
```python
count = 0
while count < 6:
    print("Contando... ",count)
    count += 1
else:
    print("Contagem encerrada!")
```
##Pular iterações em um loop
```python
for nome in 'jose':
    if nome == 's':
        continue
    print(nome)
```
##Exemplo de verificação de número primo através de loops
```python
for i in range(2,30):
    j = 2
    counter = 0
    while j < i:
        if i % j == 0:
            counter = 1
            j += 1
        else:
            j = j + 1
            
    if counter == 0:
        print(str(i)+'é um número primo')
        counter = 0
    else:
        counter = 0
```
##Usando *Range* para contagem decrescente
```python
for i in range(0,-12,-2):
    print(i)
```
##Usando *Range* para imprimir os itens da lista
```python
lista4 = ['Banana','Uva','Laranja','Maça']
comprimento_lista4 = len(lista4)
for i in range(0,comprimento_lista4):
    print(lista4[i])
```