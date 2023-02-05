# Proyecto de Backend con Python, Djando y MySQL

### Primer Paso: Crear Entorno, Instalar Django y Sincronizar con Git.

El primer paso es crear un entorno virtual para nuestro proyecto con el comando:

```
conda create -p django_mysql_api
conda activate django_mysql_api/
conda install python
```

Una vez creado, procedemos a instalar el framework django, junto con mysqlclient y pymysql de la siguiente forma:

```
pip install django
pip install mysqlclient
pip install pymysql
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
        'PASSWORD':'root',
        'NAME':'django_api', # nombre de las base de datos
        'OPTIONS':{
            'init_command':"SET sql_mode='STRICT_TRANS_TABLES'" # para que no salte advertencia al conectarnos
        }
    }
}
```

### El Tercer Paso: Crear un modelo y Conectarlo a MySQL.

Para ello utilizamos los archivos models.py y admin.py. Verificamos la conexión con el comando:

```
python manage.py migrate
```

El comando anterior creara 10 tables por defecto en la base de datos "django_api".

Ahora creamos un superusuario con el comando:

```
python manage.py createsuperuser
```

Y realizamos la migración de modelo con:

```
python manage.py makemigrations
```

Ahora probamos nuestro panel de administración django ejecutando nuestro servidor con el comando:

```
python manage.py runserver
```

### El Cuarto Paso: Crear Views y Urls

- Comienzo a crear vistas basadas en una clase.
- Archivos de rutas.
- Método GET para listar companies.
- Respuesta Json
- Descargar Thunder Client para probar requests.
- Create el Método POST
- CSRF (Cross-site request forgery) para brindar seguridad en el POST.
- Método GET para leer companies por id.