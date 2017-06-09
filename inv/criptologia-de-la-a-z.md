---
id: criptologia-de-la-a-z
title: Criptografía de la A-Z
permalink: inv/criptologia-de-la-a-z.html
---
# Criptografía de la A-Z

## Introducción - Prefacio

Por **cifrado o encriptación**, nos referimos al proceso de convertir información a una forma oculta o enmascarada para poder enviarla a través de canales potencialmente inseguros.

El proceso inverso es llamado **desencriptación o descifrado**.

tilizando fuertes técnicas de encriptación, la información valiosa y sensible puede ser protegida contra criminales organizados, hackers o espias de fuerzas militares extranjeras. Sin embargo, al movernos dentro de la sociedad de la información, el valor de la criptografía se hace evidente en todos los días de la vida en determinadas áreas como la privacidad, confianza, pagos electrónicos y control de acceso. De esta manera, el campo de la criptografía se ha ampliado desde las tecnicas de encriptación clásicas hasta áreas como la autenticación, integridad de datos, y el no-repudio de la transferencia de datos.

## Terminología Básica

A continuación, se presentarán los conceptos básicos y los metodos principales de criptografía. Cualquier opinión y evaluación presentadas aquí son especulativas, y ni el autor, ni segu-info pueden hacerce responsable de su exactitud, aunque cada intento es realizado para asegurar que la información es tan correcta y actualizada como sea posible.

Supongamos que alguien quiere enviar un mensaje a un receptor, y quiere estar seguro de que nadie mas leea el mensaje.

Sin embargo, existe la posibilidad de que alguien mas abra el correo o escuche la comunicación electrónica.

En terminos criptográficos, el mensaje es llamado **Texto Plano o Texto Claro**. El proceso de codificación del mensaje de forma tal que se oculte su contenido de extraños o intrusos es llamado encriptación o cifrado. El mensaje encriptado es llamado **Texto Cifrado**. El proceso para obtener el texto plano desde el texto encriptado es llamado desencriptación, decodificación o descifrado. La encriptación y la desencriptación generalmente hacen uso de una **Llave**, y el método de codificación es tal que la desencriptación puede ser ejecutada solamente conociendo la llave.

La **Criptografía** es el arte o ciencia de técnicas matemáticas relacionadas con aspectos de la seguridad de los datos como:

- confidencialidad o mantener secreto el contenido de la información de partes no autorizadas;
- integridad de los datos, o detección de modificaciones no autorizadas de los datos;
- autenticación o autentificación, o identificación del origen de las entidades o datos;
- no repudio, o prevenir que una entidad niegue una acción que ha realizado.

El **Criptoanálisis** es el estudio de métodos matemáticos que son utilizados en el intento de vencer las tecnicas criptográficas.
La **Criptología** es el estudio de la criptografía y del criptoanálisis.

## Algoritmos Criptográficos Básicos

El método de encriptación y desencriptación es llamado Cifrado. Algunos métodos criptográficos se basan en el anonimato de los algoritmos de encriptación; tales algoritmos son de interes histórico y no son adecuados para las necesidades del mundo real. En lugar de anonimato de los algoritmos por si solos, todos los algoritmos modernos basan su seguridad en la utilización Llaves; y un mensaje solo puede ser desencriptado si la llave utilizada para desencriptar coincide con la utilizada para encriptar.   <a href="https://goo.gl/x5q8s8" target="_blank">(Leer mas)</a>

## Algoritmos Criptográficos Fuertes

Los buenos sistemas criptográficos deberían siempre ser diseñados para que sean tan difíciles de quebrar como sea posible. Es posible construir sistemas que no puedan ser rotos en la práctica (aunque esto usualmente no puede ser probado). Esto no incrementa significativamente el esfuerzo de implementación del sistema; sin embargo, se requiere de cierto cuidado y experiencia. No hay excusa para que un diseñador de sistemas deje al sistema quebrantable. Cualquier mecanismo que pueda ser usado para sortear la seguridad debe hacerse explícito, documentado, y puesto en atención de los usuarios finales. <a href="https://goo.gl/nnJxFP" target="_blank">(Leer mas)</a>

## Firma Digital

Algunos algoritmos de clave pública pueden ser utilizados para generar firmas digitales. Una firma digital es una reducida cantidad de datos que fue creada utilizando para ello una clave privada, y donde puede ser utilizada una clave pública para verificar que dicha firma fue realmente generada utilizando la clave privada correspondiente. El algoritmo a utilizar para generar la firma debe funcionar de manera tal que sin conocer la clave privada sea posible verificar su validez. <a href="https://goo.gl/fVvOUQ" target="_blank">(Leer mas)</a>

## Criptoanálisis y Ataques a Criptosistemas

El criptoanálisis es el arte de descifrar comunicaciones encriptadas sin conocer las llaves correctas. Existen muchas técnicas criptoanalíticas. Algunas de las más importantes se describen a continuación. <a href="https://goo.gl/oX9eLD" target="_blank">(Leer mas)</a>

## Criptosistemas de Llave Pública

Con la clave pública se puede cifrar mensajes, y descifrarlos con la clave privada. Así el propietario de la clave privada sería el único que podría descifrar los mensajes, pero cualquier persona que conozca la clave pública podría enviarlos en forma privada. <a href="https://goo.gl/Gai9Io" target="_blank">(Leer mas)</a>

## Criptosistemas de Llave Privada

Los algoritmos de Llave Privada (o cifrado simétrico) usan la misma llave para la encriptación y desencriptación (o una es fácilmente derivable de la otra). Este es el acercamiento más sencillo a la encriptación de datos, es matemáticamente menos complicado que la criptografía de llave pública y ha sido usado por varios siglos.  <a href="https://goo.gl/dJGBq4" target="_blank">(Leer mas)</a>

## Funciones Hash

Las funciones Hash criptográficas son utilizadas en varios contextos, por ejemplo, para calcular el resumen del mensaje cuando se esta haciendo una firma digital. Una función Hash comprime el bit de un mensaje a un valor Hash de tamaño fijo en cierto modo que distribuye el posible mensaje uniformemente en medio de los valores Hash posibles. <a href="https://goo.gl/ZDSRb0" target="_blank">(Leer mas)</a>


## Generador de Números Aleatorios

El generador de números aleatorios puede ser fácilmente roto y puede volverse el punto mas débil de nuestro sistema criptográfico. <a href="https://goo.gl/y3z7Rb" target="_blank">(Leer mas)</a>

## Protocolos Criptográficos y Estándares

En este artículo se describen los protocolos de software usados en varias aplicaciones. Esos protocolos están construidos sobre algoritmos criptográficos de bajo nivel, como se describio en el articulo de algoritmos.  <a href="https://goo.gl/sUt3da" target="_blank">(Leer mas)</a>

<a href="https://goo.gl/10YNcM" target="_blank">*Fuente investigativas*</a>
