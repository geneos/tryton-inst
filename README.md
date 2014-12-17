tryton-inst
===========

Instalación de entorno Tryton para desarrollo

### Como instalar Tryton dentro del virtualenv

Prerequisitos: 
- postgresql instalado 
- Rol de usuario tryton con password tryton creado

## Instalar python y otros paquetes necesarios 
sudo apt-get install python-pip python-virtualenv virtualenvwrapper python-dev libldap2-dev libsasl2-dev exuberant-ctags


## Ir al home de usuario y crear una carpeta donde alojar los virtualenvs 
cd /home/usuario
mkdir tryton-desarrollo
cd trytond-desarrollo

## Crear un entorno virtual

virtualenv tryton-virtual1
cd tryton-virtual1

## Activar virtualenv e instalar paquetes necesarios

source bin/activate

pip install pip -U
pip install psycopg2 python-dateutil relatorio PyWebDAV pydot pytz openoffice-python vatnumber beautifulsoup4 vobject python-sql polib python-ldap simpleeval


##Descargar Tryton 3.2, descomprir y mover la carpeta

wget http://downloads.tryton.org/3.2/trytond-3.2.0.tar.gz
tar -xvf trytond-3.2.0.tar.gz
mv trytond-3.2.0 trytond
 
##Crear o editar el archivo etc/trytond.conf

Editar o copiar el archivo trytond.conf


##Levantar y probar si funciona creando una base

trytond/bin/trytond -c trytond/etc/trytond.conf


##Ahora instalar módulos según cada caso

pip install trytond-account==3.2
pip install trytond-company==3.2
pip install trytond-country==3.2
pip install trytond-currency==3.2
pip install trytond-party==3.2
pip install trytond-party==3.2


##Registrar los módulos

trytond/bin/trytond -i all -d TEST2

##Levantar el servidor

trytond/bin/trytond -c trytond/etc/trytond.conf



