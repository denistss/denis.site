#Flask

##Aplicação básica em Flask/Html

> Foi criado uma lógica bem simples para analisar se o número digitado é impar ou par, atribuido esta lógica em uma função *def* e criado um arquivo de nome *main.py* com o código;
```
Diretórios:
/Flask
	/-main.py
```
###Utilizando a biblioteca Flask
* Código do arquivo *main.py*;
```
from flask import Flask, request, render_template # Importando as bibliotecas;

app = Flask(__name__) # Inicializa a aplicação;

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

![flask1](img\flask1.png)