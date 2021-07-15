#Migração para o banco PostgreSQL

###Pacotes

> Instalar o pacote para conexão com o Postgress;
```pip install psycopg2```

###Exportação
> Exportar dados do banco atual em xml ou json- SQLite;
```python manage.py dumpdata --indent 3 --format xml > dados.xml```

###Edição de arquivo settings.py

Configuração da conexão com o banco Postgres;

```
DATABASES = {
    'default':{
        'ENGINE':'django.db.backends.postgresql_psycopg2',
        'NAME': 'teste',
        'USER': 'postgres',
        'PASSWORD': 'denis',
        'HOST': 'localhost',
        'PORT': '',
    }
}
```

###Migrações
Migrações para o banco Postgres;
```python manage.py migrate --run-syncdb```

###Carga da dados
Carregamento do banco Postgres com os dados exportados em xml/json;
```python manage.py loaddata dados.xml```

![FLASK1](img\img-flask\flask1.png)