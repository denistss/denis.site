#Ambiente Virtual 2

###Criando Ambiente Virtual _virtualenv_ no Windows

Considerando que voc� j� tem o Python instalado, bem como as vari�veis de ambiente e o �pip�, siga o procedimento a seguir.

� Instalar pacote para cria��o de ambientes virtuais
```
pip install virtualenv
```
� Instalar pacote para gerenciamento dos ambientes virtuais
```
pip install virtualenvwrapper-win
```
� Crie um ambiente virtual
```
mkvirtualenv nome_do_ambiente
```
� Ative o ambiente virtual rec�m criado
```
workon nome_do_ambiente
```

Agora � s� instalar os pacotes que deseja ter nesse ambiente virtual que voc� acabou de criar e ativar. Voc� pode ter quantos ambientes desejar e eles, por padr�o, ficam dentro no diret�rio Envs dentro da pasta do usu�rio. Por exemplo: C:\Users\user\Envs