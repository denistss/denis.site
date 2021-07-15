## Criando Ambiente Virtual _virtualenv_ no Windows

Considerando que voce ja tem o Python instalado, bem como as variaveis de ambiente e o pip, siga o procedimento a seguir.

>Instala pacote para criação de ambientes virtuais
```
pip install virtualenv
```
>Instalar pacote para gerenciamento dos ambientes virtuais
```
pip install virtualenvwrapper-win
```
> Crie um ambiente virtual
```
mkvirtualenv nome_do_ambiente
```
> Ative o ambiente virtual recém criado
```
workon nome_do_ambiente
```

> Agora é só instalar os pacotes que deseja ter nesse ambiente virtual que você acabou de criar e ativar. Você pode ter quantos ambientes desejar e eles, por padrão, ficam dentro no diretório Envs dentro da pasta do usuário. Por exemplo: C:\Users\user\Envs