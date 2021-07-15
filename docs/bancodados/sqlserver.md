#SQL SERVER

###Restaurar banco de dados externo

![1](img-sqlserver\1.png)

![2](img-sqlserver\2.png)

![3](img-sqlserver\3.png)

###Primeiros comandos de *Query* (Consulta)

####Comando *SELECT*

* Seleção de nomes e sobrenomes das pessoas;
```
SELECT FirstName, LastName FROM person.Person;
```
![4](img-sqlserver\4.png)

####Comando *DISTINCT*

* Seleção de nomes únicos das pessoas;
```
SELECT DISTINCT LastName FROM person.Person;
```
![5](img-sqlserver\5.png)

####Comando *WHERE*

* Seleção de pessoas com o mesmo sobrenome;
```
SELECT FirstName, LastName FROM person.Person
WHERE LastName = 'Stewart';
```

![6](img-sqlserver\6.png)

* Consulta dos produtos da tabela *Production.Product*;
```
SELECT * FROM Production.Product;
```
![7](img-sqlserver\7.png)

* Seleção de produtos de cores azul ou preta;
```
SELECT * FROM production.Product
WHERE Color = 'Black' or Color = 'Blue';
```
![8](img-sqlserver\8.png)

####Comandos *COUNT* e *GROUP BY*

* Consulta das cores de produtos disponíveis e suas quantidades;
```
SELECT Color, COUNT(Color) AS Qtd FROM production.Product
GROUP BY Color;
```
![9](img-sqlserver\9.png)

* Consulta de duas cores de produtos (preto e azul) e suas quantidades;
```
SELECT Color, COUNT(Color) AS Qtd FROM production.Product
WHERE Color = 'Black' or Color = 'Blue'
GROUP BY Color;
```
![10](img-sqlserver\10.png)

* Consulta das títulos de pessoas disponíveis e suas quantidades;
```
SELECT title, count(title) AS 'Qtd' FROM Person.Person
GROUP BY Title;
```
![101](img-sqlserver\101.png)

####Comandos *WHERE* utilizando operadores

* Consulta de produtos usando o operador _diferente <>_, para visualizar somente produtos diferentes do valor informado no _WHERE_;
```
SELECT * from production.Product
WHERE color <> 'black';
```
* Consulta de nomes de produtos entre valores específicos de peso;
```
SELECT Name,weight from Production.Product
WHERE weight > 500 and weight < 700;
```
####Comandos *TOP*

* Consulta utilizando um limitador de linhas na pesquisa;
```
SELECT TOP 5 * FROM Production.Product;
```
