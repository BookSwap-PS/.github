----------Back-End--------------------


Quando for rodar o projeto Back-end

crie sua branch com o git flow a partir da develop

com isso, no settings 

comente o DATABASE que atual e coloque:

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

assim voce irá usar o sqlite do django

para rodar utilize python manage.py runserver 0.0.0.0:8000

----------Front-End--------------------

como todas estao usando windows provalmente
abra o cmd e digite ipconfig
pegue seu ip 
vá ate a .env-example, duplique ela e renomeie para .env

em API_DEV_URL= coloque seu ip
sendo: API_DEV_URL=http://<seuip>:8000

lembre-ce tambem de colocar o seu ip nos ALLOWED_HOSTS do back-end, fica em bookswap/settings.py

Terminou suas tasks/feature/fix, testou e esta funcionando corretamente? 
apenas comente o 

DATABASES = {

    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

![image](https://github.com/user-attachments/assets/76d03abf-ee4b-4ee9-9e2c-029ac9a25499)


e tire o comentario de

DATABASES ={
  
    'default': {
    
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'bookswap',
        'USER': 'root',
        'PASSWORD': 'ps2024bk',
        'HOST': 'db',
        'PORT': '5432',
        
    }
}

![image](https://github.com/user-attachments/assets/7991f3b3-d989-4d74-b5fc-798ffea9d082)


Com isso feito envie sua branch e faça o PR para a develop com o revisor selecionado 


Essa foi a forma com que achei para poderem testar suas coisas no locahost, sabendo que muito provavelmnente nao irao querem usar Docker



