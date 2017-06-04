---
id: instalacion-backend
title: Instalación en el backend
permalink: docs/instalacion-backend.html
prev: introduccion.html
next: instalacion-frontend.html
---
# Instalación en el backend
Instalar enigma en el backend basicamente consta de 3 sencillos pasos:
* Generar el grupo de pares de llaves (que vamos a usar para encriptar).
* Implementar los archivos de enigma.
* Importar enigma.api.php

## Generar el grupo de pares de llaves
Para que enigma cifre de manera segura y aleatoria, es necesario generar un grupo de pares de llaves para que pueda utilizar.
Para esto es necesario instalar <a href="https://www.openssl.org/" target="_blank">OpenSSL</a> y generar las llaves con los siguientes comandos (y en ese orden) en la terminal.<br>

Estos comandos aplican para sistemas de la familia unix como mac, gnu/linux o freebsd por ejemplo.
```
$ openssl genrsa -out priv.pem 2048
$ openssl rsa -pubout -in priv.pem -out pub.pem
```

Los anteriores comandos nos van a generar 2 archivos, **priv.pem** y **pub.pem**, es decir, la llave privada y la llave pública respectivamente.<br>
**Esto es sólo nuestro primer par de llaves**, las cuales debemos guardar en una carpeta numerada para luego guardarla en una carpeta */keys*.<br>
Debemos repetir este proceso para generar cuantos mas pares queramos, con esto el algoritmo tendrá diferentes pares de llaves para escoger aleatoriamente.<br>

El número de pares de llaves a generar que recomendamos para cualquier proyecto, es de **entre 3 y 20 pares.** <br>
Resultando así en una estructura como la siguiente.
```
mi-proyecto/
    enigma/
        keys/
            01/
                priv.pem
                pub.pem
            02/
                priv.pem
                pub.pem
            03/
                priv.pem
                pub.pem
```
En donde en la carpeta **keys** he guardado un grupo de 3 pares de llaves distintas. Cada par en una carpeta numerada.
Y todo esto dentro de la carpeta **enigma** que es donde vamos a guardar la librería también.<br>

## Implementar los archivos de enigma
Una vez que tenemos los pares de llaves con los que va a trabajar enigma sólo resta pegar los archivos:
* enigma.api.php
* pollify.php
* sqAES.php

dentro de la carpeta enigma, al mismo nivel de la carpeta keys donde estan las llaves.<br>
Quedando la siguiente estructura:
```
mi-proyecto/
    enigma/
        keys/
            01/
                priv.pem
                pub.pem
            02/
                priv.pem
                pub.pem
            03/
                priv.pem
                pub.pem
        enigma.api.php
        pollify.php
        sqAES.php
```

## Importar enigma
Para este ejemplo creamos un archivo **controlador.php** en la raiz del proyecto, y dentro del cual vamos a importar enigma como cualquier importación en php.
```
<?php
require_once "enigma/enigma.api.php";
```
Y así quedaría correctamente instalado enigma en el backend, con la siguiente estructura en nuestro ejemplo:
<div class="md-div-center">
<img alt="imagen" src="{{ site.baseurl }}/img/estructura-backend.png">
</div>
