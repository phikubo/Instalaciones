# Cómo instalar workon (virtualenvwrapper) en Ubuntu 19.10
Guía de Instalación de Software Libre

Esta guía está basanda en el siguiente enlace: https://itnext.io/virtualenv-with-virtualenvwrapper-on-ubuntu-18-04-goran-aviani-d7b712d906d5


##Paso 1
Crea una carpeta oculta (o no, según tus preferencias):
(en bash)>>mkdir .virtualenv
##Paso 2
Como te habrás dado cuenta, cuando escribes "python" en la bash, python no se ejecutá, en su lugar, sí ejecuta "python3". Debido a esto, instala pip (si no lo tienes instalado):
(en bash)>>sudo apt install python3-pip
##Paso 3
Instala la aplicación para entornos virtuales
(en bash)>>pip3 install virtualenv
##Paso 4
Instala el wrapper para usar workon
(en bash)>>pip3 install virtualenvwrapper
##Paso 5
Verifica los lugares de instalación de ambas aplicaciones:
(en bash)>>which virtualenv
(en bash)>>which virtualenvwrapper 
Norlamente el segundo comando no ejecuta nada ni provee mayor información
##Paso 6
Abre el documento de configuración para bash:
(en bash)>>gedit .bashrc
Esto abrirá un documento.
##Paso 7
Dirígete al final del documento y es escribe las siguientes líneas:

export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3         
#---->>>este directorio lo provee (en bash)>>which python3
export WORKON_HOME=$HOME/.virtualenvs
#esta es la dirección de la carpeta creada en paso 3
export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenvwrapper.sh   
#---->>> esta dirección la provee el paso 5
source /usr/local/bin/virtualenvwrapper.sh 


Si sale un error de que no encuentra el archivo .sh, busca la dirección como sigue y reemplazalo en donde dice source (línea anterior)
(en bash)>>find / -name virtualenvwrapper.sh

##Paso 8
Guarda el archivo y abre una nueva terminal. Ahora podras crear entornos virtuales y usar la palabra clave workon <nombre_de_tu_entorno_virtual> para acceder a el (claro, previamente creados, ver: https://virtualenvwrapper.readthedocs.io/en/latest/command_ref.html)
