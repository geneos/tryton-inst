tryton-inst
===========

##  Instalación de entorno Tryton 3.2 para desarrollo
###  Instalación utilizando virtualenv + PIP

####Prerequisitos: 
- Tener postgresql instalado y corriendo 
- Crear en postgres un rol de usuario "tryton" con password "tryton"

####Instalar python y otros paquetes necesarios 

`sudo apt-get install python-pip python-virtualenv virtualenvwrapper python-dev libldap2-dev libsasl2-dev`


####Ir al home del usuario y crear una carpeta nueva donde alojar los distintos virtualenvs 

`cd /home/usuario`

`mkdir tryton-desarrollo`

`cd trytond-desarrollo`


####Crear el entorno virtual

`virtualenv tryton-virtual`

`cd tryton-virtual`


####Activar virtualenv e instalar paquetes necesarios

`source bin/activate`

`pip install pip -U`

`pip install psycopg2 python-dateutil relatorio PyWebDAV pydot pytz openoffice-python vatnumber beautifulsoup4 vobject python-sql polib python-ldap simpleeval`


####Descargar Tryton 3.2, descomprir y mover la carpeta

`wget http://downloads.tryton.org/3.2/trytond-3.2.0.tar.gz`

`tar -xvf trytond-3.2.0.tar.gz`

`mv trytond-3.2.0 trytond`
 
 
####Crear o editar el archivo etc/trytond.conf

Editar el archivo trytond.conf. Modificar las siguientes líneas:

 `jsonrpc = *:8000 `
 
 `db_host = localhost `
 
 `db_port = 5432 `
 
 `db_user = tryton `
 
 `db_password = tryton `
 
 `# Timezone of the server `
 
 `timezone = America/Argentina/Buenos_Aires `
 
 `admin_passwd = admin `


####Iniciar el servidor (probar si todo funciona creando una base)

`trytond/bin/trytond -c trytond/etc/trytond.conf`


####Instalar módulos según cada caso
Tryton sólo trae tres módulos por defecto: ir, res, webdav.
Para instalar los módulos necesarios ejecutar los siguientes comandos PIP:

`pip install trytond-account==3.2`

`pip install trytond-company==3.2`

`pip install trytond-country==3.2`

`pip install trytond-currency==3.2`

`pip install trytond-party==3.2`

`pip install trytond-party==3.2`


####Para registrar los módulos en la base ya creada

`trytond/bin/trytond -i all -d TESTDB`

donde: TESTDB es el nombre de la base de datos


####Iniciar el servidor

`trytond/bin/trytond -c trytond/etc/trytond.conf`



