---
id: como-la-criptografia-ayuda
title: Cómo la criptografía ayuda
permalink: inv/como-la-criptografia-ayuda.html
---
# Cómo la criptografía en el DNS ayuda a reducir el abuso
<h4 align="right">Fecha: 9-abr-2015</h4>

En mi penúltima nota escribí acerca del Sender Policy Framework (SPF), que permite autorizar direcciones IP para el envío de email asociado a un nombre de dominio. Ahora me referiré al DomainKeys Identified Mail o DKIM, que es un estándar de Internet (ver RFC 4871) que permite reducir el spam, el phishing y otras cuantas formas de abuso.

## Generalidades acerca de DKIM

Mientras que SPF es un servicio que permite determinar si una dirección IP está autorizada para enviar email asociado a un dominio, **DKIM permite determinar si el remitente del mensaje es en realidad quien él dice ser (autenticación) y si el mensaje fue alterado durante el tránsito del remitente al destinatario (integridad)**.

Funciona de manera sencilla, utilizando criptografía de llave pública: el remitente crea un par de llaves criptográficas, al igual que haría al usar PGP o GPG (llave pública y llave privada). Publica la llave pública como un registro de texto (o TXT record) en el archivo de zona de su dominio (vea al final de mi nota sobre SPF más información sobre archivos de zona y TXT records). Al enviar un mensaje, utiliza la llave privada para generar el hash (¿qué es un hash?) y firmarlo digitalmente.

Los servidores de correo utilizan la llave pública, que ha sido publicada como un recurso en el Sistema de Nombres de Dominio, para determinar si el mensaje es auténtico (enviado por quien se dice que lo envió) e íntegro (que permanezca inalterado desde su envío).

## ¿Cómo funciona DKIM en la práctica?

Esta imagen, que tomé prestada de mi colega Dave Piscitello -autor del blog securityskeptic.com y compañero de trabajo en la oficina- lo explica (la traducción al español es mía):

<div class="md-div-center">
<img alt="imagen" src="{{ site.baseurl }}/img/mapa1.png" class="md-img md-center">
</div>

## ¿Cómo se ve la llave pública de DKIM en un encabezado de email?

Cuando se envía un mensaje asociado a un dominio que tenga una llave pública de DKIM en su archivo de zona, el servidor de correo saliente añade al encabezado del mensaje unos campos de datos que incluyen, entre otros, el dominio (d=) y el selector (s=), que permite asociar varias llaves públicas a un solo dominio). En este ejemplo que copio abajo, que tomé de un email que me fue enviado desde una cuenta de Gmail, estos corresponden a d=gmail.com y s=20120113:

DKIM-Signature: v=1; a=rsa-sha256; c=relaxed/relaxed;
d=gmail.com; s=20120113;
h=mime-version:date:message-id:subject:from:to:content-type;
bh=qZftPw2NfXGT5S23BhPcIpAE0+0J60IqZAqxFNGgPMg=;
b=Yyu956SwUt+GqOZjxa31xjelR3KOCKEWrVZhwagqsm63+bi+YczYu205enssirMveuYABOFkcvuvoE3Pc39godrebW19HkgXlr7YlBpnQEZQQeHVa2SXdjehxixbneTfmfYEgs3oPytF41fQ1fYGhbvgGg38zS3pkc4Jlyexlu9uuuRhoVHNvUA3cx5BzBah9d5JVmvVpwg3KgRKrDV1e4chF4IZLHPt7sipSlBbODplNknFro4eCAwak1gfyjhhRo4mmJPNXOrR4hr54XbPuihoEVQ8GtHUlqvGTBaGa5cA8mVEl2aOD9Ybz5Apev81qTI1kphZlESQ4T1fbra2VQ==

## ¿Cómo se ve la llave pública de DKIM en el archivo de zona del dominio?

Cuando el mensaje es recibido por el servidor de correo del destinatario, el servidor envía una consulta al DNS buscando en el archivo de zona del dominio el registro de texto que contiene la llave pública. Lo que recibe es algo muy parecido a lo que sigue acá abajo, que es parte del resultado que se obtiene al usar el comando ‘dig’ (o Domain Information Gropper).

; <<>> DiG 9.8.3-P1 <<>> 20120113._domainkey.gmail.com txt

;;QUESTION SECTION:
;20120113._domainkey.gmail.com. IN TXT

;; ANSWER SECTION:
20120113._domainkey.gmail.com. 300 IN TXT “k=rsa\; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA1Kd87/UeJjenpabgbFwh+eBCsSTrqmwIYYvywlbhbqoo2DymndFkbjOVIPIldNs/m40KF+yzMn1skyoxcTUGCQs8g3FgD2Ap3ZB5DekAo5wMmk4wimDO+U8QzI3SD0”“7y2+07wlNWwIt8svnxgdxGkVbbhzY8i+RQ9DpSVpPbF7ykQxtKXkv/ahW3KjViiAH+ghvvIhkx4xYSIc9oSwVmAl5OctMEeWUwg8Istjqz8BZeTWbf41fbNhte7Y+YqZOwq1Sd0DbvYAD9NOZK9vlfuac0598HY+vtSBczUiKERHv1yRbcaQtZFh5wtiRrN04BLUTD21MycBX5jYchHjPY/wIDAQAB"

Aunque esto pueda parecer complejo, en realidad **DKIM es transparente para el usuario, no requiere de mayores actualizaciones para el software de correo** (el llamado técnicamente Mail User Agent o MUA), se puede extender a muchos usuarios bajo el mismo dominio, tiene bajos costos de desarrollo e implementación y no requiere de los servicios de un tercero, aunque depende del Sistema de Nombres de Dominio (estos beneficios y otros temas son mencionados por Dave Crocker acá. Como dato curioso, Dave es hermano del presidente de la Junta Directiva de ICANN, Steve Crocker).

Mike Delany de Yahoo! diseñó la primera versión de lo que hoy es DKIM, que, tras el trabajo del grupo en el que estaban otros desarrolladores de Sendmail, PGP Corporation y la misma Yahoo!, se convirtió en el estándar definido por el RFC 4871 citado arriba. Una lista de organizaciones que han implementado DKIM está disponible acá.

El proyecto OpenDKIM es una implementación de código abierto de DKIM y ofrece un paquete sin costo para que quienes lo deseen puedan implementar y usar el estándar.

¿Su organización ya implementó DKIM? Le sugiero preguntar a su departamento de sistemas y hacer lobby, en caso de que no lo haya sido aún, para que lo sea.

<a href="https://goo.gl/SAv4fx" target="_blank">*Fuente*</a>
