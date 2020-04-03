#Microframework Flask

##Aplicação básica em Flask e Html

###Arquitetura do Flask

> Antes de iniciarmos a nossa aplicação em si primeiro vamos entender, de uma forma resumida, como funciona a arquitetura do sistema;
O *Flask* utiliza uma arquitetura de modo **MVC**_(Model-Viewl-Controller)_ onde existem 3 camadas que conversam entre si.
MVC é nada mais que um padrão de arquitetura de software, separando sua aplicação em 3 camadas: A camada de interação do usuário _(View)_, a camada de manipulação dos dados _(Model)_ e a camada de controle _(Controller)_;
**Model**: Responsável pela leitura e escrita de dados, e também de suas validações, ou seja, seu papel sempre será de manipulação de dados;
**View**: Responsável por fazer a interação com o usuário, fazendo a exibição de sua interface através de linguagens de marcação como: html e xml;
**Controller**: Responsável por receber as requisições do usuário e controlar qual model será usado e em qual view será exibida;

![FLASK11](../img/img-flask/flask11.png)

> Foi criado uma lógica bem simples para analisar se o número digitado é **Par** ou **Impar**, em seguida atribuido esta lógica em uma função *def* que irá executar todo este trabalho de decisão. Vamos colocar o todo o código no arquivo de nome *main.py*;
```
Diretórios:
/Flask
	/-main.py
```
###Utilizando a biblioteca Flask
* Código do arquivo *main.py*;
```
from flask import Flask, request, render_template # Importando as bibliotecas;

app = Flask(__name__) # Criado uma instância;

@app.route('/') # Cria uma rota;
def main():
	resultado = None
	numero = request.args.get('numero') # Utilizado verbo GET do protocollo http;

	if numero is not None: # Correção na variável numero para não vir como NoneType;
		numero = float(numero)
		
		n = ( numero % 2)

		if n == 0:
 			resultado = 'Este número é Par'
		else:
 			resultado = 'Este número é Impar'

	return render_template('index.html', resultado=resultado)

if __name__ == '__main__':
  app.run(debug=True) # Executa a aplicação;
```

* Observasões do código:
&nbsp;
```
app = Flask(__name__)
```
Criado uma instância dentro da variável *app*, em seguida foi atribuido a variável especial *__name__* a esta instância que o interpretador do *Python* irá decidir se executará como arquivo principal *__main__* ou como arquivo secundário etc.;
&nbsp;
```
@app.route('/')
def main():
```
O *Python* têm um *método* de trabalho de nome *decorator* que tem o poder de atrelar funções, ou seja, usando funções como argumento de outras funções. Neste caso, o *método route* padrão do *python* dentro do *flask*, cria uma rota para a função que criamos em seguida, que neste caso demos o nome *main* para a função; 

&nbsp;
Foi importado a biblioteca *request* e utilizado o método *request.args.get* para obter os valores digitados pelo usuário e guardar na variável *numero*;

&nbsp;
Foi necessário criar um *if* para a variável *numero* retornar em *type float* e não retornar como *NoneType*(tive este problema anteriromente e resolvi com este if);

###Formatação de Template Jinja/Html
* Criado outro arquivo de nome *index.html* e digitado o código abaixo;
```
Diretórios:
/Flask
	/-main.py
	/templates
		/-index.html
```
* Código do arquivo *index.html*;
```
<html>
    <head>
        <title>Minha primeira aplicação em Flask</title>
    </head>
    <body>
        Par ou Impar?

        <div>
            <form method="get">
                Digite um número:
                <input type="text" name="numero">
                <br>
                <input type="submit" value="Enviar">
            </form>
        </div>

        {% if resultado %}
        <div>
            {{resultado}}
        </div>
        {% endif %}

    </body>
</html>
```
* Observasões do template:

&nbsp;
Para funcionar a inserção do número pelo html, na *tag input* é necessário criar um atributo *name* com o valor do mesmo nome da variável que receberá este valor, no caso a variável *numero*;

&nbsp;
O *if* na que está no html faz parte da sintaxe do Jinja;

&nbsp;
As sintaxe *{{resultado}}* no *div* fazem aparecer o resultado da verificação final do número, apenas se a variável *resultado* não for *None*;

&nbsp;
Perceba que colocamos o template *index.html* dentro da pasta templates, pois o *Flask* por padrão lê os templates dentro desta pasta, então só precisamos colocar no *render_template* o nome do nosso template e não o caminho deste diretório;

&nbsp;
Agora é só rodar nossa aplicação executando o comando *python main.py* no prompt e abrir a URL *http://127.0.0.1:5000/* ou *http://localhost:5000/*;

* Nossa aplicação ficará com esta cara:

![FLASK1](../img/img-flask/flask1.png)