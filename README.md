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



####Crear el entorno virtual dentro de la carpeta tryton-desarrollo

`cd trytond-desarrollo`

`virtualenv tryton-virtual`



####Activar virtualenv e instalar paquetes necesarios

`cd tryton-virtual`

`source bin/activate`

`pip install pip -U`

`pip install psycopg2 python-dateutil relatorio PyWebDAV pydot pytz openoffice-python vatnumber beautifulsoup4 vobject python-sql polib python-z3c python-ldap simpleeval`


####Descargar Tryton 3.2, descomprir y mover la carpeta

`wget http://downloads.tryton.org/3.2/trytond-3.0.4.tar.gz`

`tar -xvf trytond-3.0.4.tar.gz`

`mv trytond-3.0.4 trytond`
 
 
####Crear o editar el archivo etc/trytond.conf

Editar el archivo trytond.conf o descargarlo desde este repositorio
Debe estar ubicado en trytond/etc


####Iniciar el servidor (probar si todo funciona creando una base)

`trytond/bin/trytond -c trytond/etc/trytond.conf`


####Instalar módulos según cada caso
Tryton sólo trae tres módulos por defecto: ir, res, webdav.
Para instalar los módulos necesarios ejecutar los siguientes comandos PIP:

pip install trytond-account==3.0.4
pip install trytond-account_invoice==3.0.4
pip install trytond-account_product==3.0
pip install trytond-company==3.0
pip install trytond-product==3.0
pip install trytond-sale==3.0
pip install trytond-product_price_list==3.0
pip install trytond-stock==3.0


####Para registrar los módulos en la base ya creada

`trytond/bin/trytond -i all -d TESTDB`

donde: TESTDB es el nombre de la base de datos


####Iniciar el servidor

`trytond/bin/trytond -c trytond/etc/trytond.conf`



