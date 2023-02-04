# Proyecto de Backend con Python, Djando y MySQL

### Primer Paso: Crear Entorno, Instalar Django y Sincronizar con Git.

El primer paso es crear un entorno virtual para nuestro proyecto con el comando:

```
conda create -p django_mysql_api
conda activate django_mysql_api/
```

Una vez creado, procedemos a instalar el framework django de la siguiente forma:

```
pip install django==3.2.4
```

Tambien creamos el archivo .gitignore para ignorar la ruta de nuestri entorno virtual. Y creamos un repositorio en GitHub para darle continuidad a nuestro proyecto, una vez creado, lo sincronizamos con nuestra carpeta con los siguientes comandos:

```
git init
git add .
git commit -m "Creación del Proyecto"
git remote add origin https://github.com/IsaacArredondo/django_mysql_api.git
git push -u origin main
```

### Segundo Paso: Crear Proyecto_API,  la APP (api) y Configuración.

Para crear nuestra carpeta de trabajo y la api usamos los comandos.

```
django-admin startproject Proyecto_API
django-admin startapp api
```

En la parte INSTALLED_APPS del archivo setting.py agregamos la aplicación "api". Y en la parte de DATABASES agregamos el siguiente código:

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'HOST':'localhost',
        'PORT':'3306',
        'USER':'root',
        'PASSWORD':'123456',
        'NAME':'django_api', # nombre de las base de datos
        'OPTIONS':{
            'init_command':"SET sql_mode='STRICT_TRANS_TABLES'" # para que no salte advertencia al conectarnos
        }
    }
}
```

### El Tercer Paso: Crear un modelo.