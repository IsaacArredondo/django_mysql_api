# Proyecto de Backend con Python, Djando y MySQL

### Primer Paso

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
