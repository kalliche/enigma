---
id: openssl-corregira-fallos-graves
title: OpenSSL corregirá fallos graves
permalink: inv/openssl-corregira-fallos-graves.html
---
# OpenSSL corregirá el próximo jueves varios fallos graves de seguridad.
<h4 align="right">Fecha: 8-nov-2016</h4>

<div class="md-div-center">
<img alt="imagen" src="{{ site.baseurl }}/img/open.png" class="md-img md-center">
</div>

Heartbleed es, sin duda, el peor fallo de seguridad al que se ha enfrentado Internet. Este fallo de seguridad en las librerías OpenSSL, librerías de cifrado más utilizadas en todo el mundo, permitía a los usuarios recuperar datos de la memoria de los servidores remotos con total facilidad. Aunque este fallo fue solucionado al poco de darse a conocer, esta librería sigue dejando ver, cada poco tiempo, nuevos fallos de seguridad.

Hace algunas horas, los responsables del desarrollo de OpenSSL han anunciado que el próximo 10 de noviembre van a liberar una nueva actualización de la librería, **concretamente la versión 1.1.0c**, la cual se centra en solucionar varios fallos de seguridad, la mayoría de ellos bastante graves, además.

Aunque, por motivos de seguridad, estos fallos no se han hecho públicos, ni se harán hasta que la actualización se encuentra ya disponible para todos los usuarios, uno de los fallos que sí se conoce ya y que será solucionado en la próxima versión es **CVE-2016-6307**, un fallo de poca importancia que permite a un atacante hacer una llamada a la función **tls_get_message_header()** para realizar un ataque de denegación de servicio.

Otro de los fallos que serán solucionados en el próximo OpenSSL 1.1.0c, esta vez más importante, se ha dado a conocer por un ingeniero de Google, quien descubrió que **el parche para la vulnerabilidad CVE-2016-6307 abría otra nueva vulnerabilidad, CVE-2016-6309**, la cual puede permitir desde la ejecución de código aleatorio en la memoria hasta dejar sin servicio el equipo.

## Debemos actualizar OpenSSL lo antes posible el próximo 10 de noviembre

Como hemos dicho, los responsables del proyecto han confirmado que **el próximo jueves 10 de noviembre de 2016 liberarán dicha actualización** solucionando los errores de seguridad antes mencionados y otros muchos que aún no se han dado a conocer. Si tenemos un servidor con cliente con OpenSSL, es recomendable actualizar a la nueva versión lo antes posible ya que, como siempre, los piratas informáticos empezarán a explotar los fallos tan pronto como se den a conocer.

Si tenemos una página web y nos preocupamos de la seguridad, antes que OpenSSL debemos utilizar otras librerías alternativas que cuentan con un mantenimiento bastante superior, como es el caso de **LibreSSL** (fork de OpenSSL por y para la comunidad) o **BoringSSL** (la alternativa desarrollada y mantenida por Google) de manera que podamos estar protegidos frente a los cada vez más frecuentes fallos en esta librería.

Estaremos pendientes del lanzamiento del nuevo **OpenSSL 1.1.0c** y os informaremos de su disponibilidad tan pronto como esté disponible.

**¿Crees que OpenSSL conseguirá volver a ser una librería tan segura como debería ser?**
