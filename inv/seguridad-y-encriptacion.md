---
id: seguridad-y-encriptacion
title: Seguridad y Encriptación
permalink: inv/seguridad-y-encriptacion.html
---
# Seguridad y Encriptación

Con la aparición de Internet y la mayor importancia que se le va dando a la información día tras día , la tecnología que antes era utilizada sólo por la Militar o Gobiernos ha cobrado mayor importancia, pero....como funciona ?

## Que es Encriptación ?

Toda encriptación se encuentra basada en un Algoritmo, la función de este Algoritmo es básicamente codificar la información para que sea indescifrable a simple vista , de manera que una letra *"A"* pueda equivaler a :*"5x5mBwE"* o bien a *"xQE9fq"*, el trabajo del algoritmo es precisamente determinar como será transformada la información de su estado original a otro que sea muy difícil de descifrar.

Una vez que la información arrive a su destino final, se aplica el algoritmo al contenido codificado *"5x5mBwE"* o bien a *"xQE9fq"* y resulta en la letra "A" o según sea el caso, en otra letra. Hoy en día los algoritmos de encriptación son ampliamente conocidos,es por esto que para prevenir a otro usuario "no autorizado" descifrar información encriptada, el algoritmo utiliza lo que es denominado **llave ("key")** para controlar la encriptación y decriptación de información. Algunos algoritmos son **DES** (algoritmo simétrico) AES que posiblemente suplantará a DES y uno de los más conocidos RSA (algoritmo asimétrico)

## Que función tiene la llave ("key") ?

Existen dos tipos de llaves ("key's") , pero la de mayor uso en Internet es denominada "public key" o algoritmo asimétrico. El nombre "public" proviene de su funcionamiento: existe una llave pública que es dada a conocer a cualquier persona que así lo desee (todo Internet), esta llave pública es utilizada por los emisores de mensajes para encriptar información , sin embargo, existe otra llave ( su pareja por llamarla de alguna manera) única que es conocida exclusivamente por el destinatario del mensaje, y es mediante esta llave única | secreta que el destinatario descifra ("decripta") los mensajes encriptados por el emisor.

## Firmas Digitales ("Digital Signatures")

Una **firma digital** utiliza el mismo funcionamiento del "public key" o algoritmo asimétrico mencionado anteriormente.

Como se mencionó, existe una "llave pública" y una "llave secreta", en el caso de **firmas digitales** la llave pública que es ampliamente conocida es capaz de identificar si la información proviene de una fuente fidedigna.En otras palabras, la llave pública será capaz de reconocer si la información realmente proviene de la "llave secreta" en cuestión.Ejemplo:

El departamento de compras posee las llaves públicas de todos los empleados de la compañía, si llega un pedimento con la dirección de email del Director de Finanzas, Cómo puede asegurarse el departamento de compras que en realidad esta persona realizó el pedimento y no alguna otra que sobrepuso el email ?. La llave secreta del director de finanzas debe de encontrarse solo en su computadora, por lo tanto al enviar el mensaje electrónico esta llave pública se añadió al email,y por lo tanto las llave publicas determinarán si la llave secreta coincide con la del director.

## Firmas Digitales en Internet

En el caso anterior de un Intranet, todas las llaves públicas provienen de una fuente fidedigna, esto es, las llaves "publicas" que posee el departamento de compras son autenticas ya que TODAS pertenecen sólo a empleados dentro de la compañía , la única posibilidad de fraude que existe,es si alguien trata de forjar la "llave secreta" de un empleado para hacerse pasar por otro.

### Pero que sucede cuando este departamento de compras empiece a realizar transacciones en Internet ?

Ellos anuncian su "llave publica" para todos los usuarios de Internet, y como solo ellos poseen la "llave secreta" sólo ellos podrán descifrar("decriptar") la información. Pero ahora, surge la siguiente pregunta: Quien le garantiza a los usuarios de Internet que esta "llave publica" REALMENTE proviene de este departamento de compras ?

Para esto existen los **certificados digitales** que son emitidos por "agencias autorizadas" como Thawte o Verisign las cuales dan el VoBo("Visto Bueno") sobre la "llave publica".

Existen pocas compañías que realizan este servicio,pero debido a la naturaleza de las "llaves publicas" siempre debe de existir una agencia central que sea capaz de decir "Si, esta llave publica proviene del departamento de compras" eso es todo su servicio, esto garantiza a los usuarios finales de "Internet" que la "llave publica" ha sido reconocida por una autoridad confiable Thawte o Verisign

La secuencia de eventos es la siguiente:

1. Se adquiere un "Certificado Digital" de Thawte o Verisign ( Costo aprox:$100-$350 Dlls U.S    Anuales,variación depende de su uso)
2. Se coloca este certificado digital ("llave publica") en el servidor de páginas y se configura para que éste envíe información encriptada según sea necesario.
3. Cuando un usuario en Internet solicite información encriptada de nuestro sitio se envía esta "llave publica" para que pueda encriptar la información y enviarla de una manera segura al sitio.
4. Al recibir la "llave publica" el navegador ("Netscape" o "Explorer") del usuario final corrobora que en realidad esta "llave publica" proviene de quien dice, en este caso, la "llave publica" dice: "Soy la llave publica de osmosislatina.com y fui emitida por Verisign mi serie es:u7767DbXs4br342Dbnn6".
5. El navegador corrobora con Verisign (en este caso) y continua o avisa al usuario final el estado de la "llave publica".

- **NOTA:** Si el navegador ("Netscape" o "Explorer") no corrobora la veracidad del "certificado digital" no implica que la información será enviada de manera insegura , la encriptación seguirá siendo valida. Lo que sucederá es que cuando sus visitantes entren a páginas que requieran encriptación ( transacciones financieras ) , el Navegador desplegara un mensaje a sus visitantes indicándoles que la fuente de encriptación ("llave publica") es insegura; esto se debe a que nadie puede avalar su "llave publica", de nuevo **lo anterior no implica que la encriptación es invalida** solo insegura.
- En ocasiones lo anterior es suficiente para hacer desconfiar al usuario final o inclusive exponerse a que un tercero este generando esta "llave publica"

## Encriptación de 40-bits y 128-bits.

Existen varios niveles de encriptación, pero las combinaciones más comunes son 40-512 bits ("llave secreta--llave pública") y 128-1024 bits ("llave secreta--llave pública"). La versión 128-1024 bits es el tipo de encriptación más fuerte que existe en el mercado. Actualmente U.S.A prohibe la exportación de productos con este tipo de Tecnología, pero cabe mencionar que ya existen varios productos producidos en Europa con esta Tecnología que no poseen tales restricciones de exportación.

La gran mayoría de los sitios en Internet utilizan la encriptación 40-512 bits, la encriptación 128-1024 bits es utilizada generalmente en transacciones de alto riesgo, como las bancarias.

## Es segura la encriptación que existe hoy en día ?

**Depende quien la intente observar !**, aunque la información sea enviada encripatada, cualquier persona en Internet con entrenamiento mínimo puede interceptar esta información encriptada, sin embargo, para observarla requiere de su "llave privada".

Y es aquí donde depende quien intente observar esta información, considere que una computadora personal (PC) puede realizar millones de operaciones por segundo, debido a esto, no es tan ilusorio **generar una "llave privada"** a partir de cierta información interceptada ; las "llaves privadas" generalmente constan de 40-bits, en una PC es posible (aunque tardado) **procesar** estas 2^40 alternativas, ahora bien, si se tienen varios servidores en paralelo realizando trillones de operaciones por segundo probablemente sea posible **procesar** estas 2^40 alternativas en cuestión de **minutos**.

Lo anterior es una de la razones por las que U.S.A cuida (cuidaba!) con tanto recelo la exportación de encriptación de 128-bits, la cual es 3 veces más poderosa (2^128 alternativas) que la de 40-bits.

Públicamente se conoce que en los servidores más poderosos del mercado es posible descubrir una "llave privada" en cuestión de días de procesamiento. Esto obviamente detiene aquellas personas ("hackers") con servidores "comunes" y en este caso hasta oficinas de seguridad gubernamentales en "decriptar" información con este tipo de encriptación

<a href="https://goo.gl/E98eZP" target="_blank">*Fuente investigativas*</a>
