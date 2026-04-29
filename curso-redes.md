## ¿Qué es Internet?

Como resumen podemos decir que Internet es como se denomina comúnmente una red de redes, una gran red donde confluyen muchísimas redes alrededor del mundo. Los proveedores  de internet (ISP: internet services providers), que nos ofrecen su servicio, tiene una topología montada de routers, swiches, nodos, servidores etc. que están conectados a internet. Así mismo las Universidades los gobiernos las fuerzas armadas organizaciones y empresas etc., de todo el mundo, están conectadas a internet de diferentes formas ofreciendo sus diversos servicios. Internet permite que todas estas redes se comuniquen entre ellas y con los usuarios de entre casa.

## ¿Qué es una IP?

Las redes se basan en el protocolo TCP/IP que en realidad son dos protocolos.
Un protocolo es una convención tomada para que a la hora de la comunicación entre dos dispositivos conectados a la red lo hagan de una forma que puedan entenderse entre si y ordenadamente. Así como nosotros tenemos una convención de comunicación con otras personas para entendernos correctamente.
Explicado de forma simple este protocolo consiste en dividir la información a enviar a otro dispositivo en paquetes pequeños a una dirección única que identifica al destinatario en la red. Esta dirección se denomina IP y únicamente identifica al destinatario de la información.
Podemos decir entonces que una IP Publica es la dirección única que tu dispositivo tiene para ser identificado en internet y es única en todo el mundo.
Dentro de las direcciones IP existen las IPv4 y las IPv6 (Versión 4 y versión 6).
IP quiere decir "Internet Protocol" y consisten en cuatro números separados por un punto que van desde el 0 al 255 en el caso de IPv4 (ej.: 127.212.14.86)
En el mundo hay cuatro mil millones de IP publicas. En un principio había un organismo encargado de entregar estas IP a las empresas que lo solicitaban. Ahora a nivel mundial hay cinco RIR (Regional Internet Registry) que son los encargados de otorgar estas IP por regiones.


![[Pasted image 20240703191938.png]]

Antes, Internet se movía principalmente en entornos de universidades de EE.UU., y los cuatro mil millones de IP de IPv4 eran suficientes para todos los dispositivos conectados. Hoy en día, la cantidad de dispositivos conectados a la red supera con creces este número. Por consiguiente, los proveedores de servicios de Internet (ISP) deben rotar las IP que tienen disponibles entre los dispositivos que se desconectan y aquellos que se conectan en ese momento.

En el momento en que te conectas, se te asigna una IP pública única y exclusiva para ti, que se utiliza para la conexión llamada WAN (Wide Area Network). Esta IP pública es temporal y puede cambiar cada vez que te reconectas, a menos que contrates una IP fija

## ¿Qué es una WAN y una LAN?

WAN significa WIDE AREA NETWORK (Red de Área Extensa)
Cuando por ejemplo haces una búsqueda en GOOGLE este responde a tu IP publica mandándote el resultado de la búsqueda. Pero si en tu casa hay mas de un dispositivo como suele pasar Google responderá a la misma IP publica para todos los dispositivos y se identificara cual dispositivo hiso la petición con la IP privada de la red de tu hogar o empresa.
Esta red es la LAN (Local Area Network o Red de Área Local) que maneja el mismo formato de IP de cuatro números separados por un punto (ej.: 192.168.0.1)
Resumiendo en el caso de tu comunicación con Google estas moviéndote en una WAN y dentro de tu casa te mueves en una LAN con la IP privada. Cuando envías datos a través de internet, estos datos salen de tu LAN y viajan a través de la WAN, utilizando la dirección IP pública de tu router para comunicarse con otros dispositivos y servicios en la red global. En resumen, el router en tu casa actúa como el punto de conexión entre tu LAN (donde se usan direcciones IP privadas) y la WAN (donde se usan direcciones IP públicas), permitiéndote acceder a internet y comunicarte con servicios externos.

## ¿Que es NAT?


El proceso que sigue el router de traducir una IP privada a una IP pública, traer los datos solicitados a la red y traducir la IP pública de vuelta a la IP privada correcta se denomina NAT (Network Address Translation).
Este proceso permite que múltiples dispositivos en una red local (LAN) compartan una única dirección IP pública para acceder a Internet. NAT mapea las direcciones IP internas privadas a una dirección IP pública y, al recibir respuestas de Internet, traduce esas respuestas de vuelta a las direcciones IP internas correspondientes.

## ¿Que es la Puerta de Enlace o Gateway?

Sintéticamente, diremos que el Gateway es el equipo que se encarga de darte acceso a internet, es decir, el router. Esto significa que en la configuración de una puerta de enlace deberíamos poner la dirección IP de nuestro router."

El Gateway (o puerta de enlace) actúa como un punto de acceso entre la red local y otras redes, generalmente  Internet. Por lo tanto, al configurar dispositivos en la red, la dirección IP del router se utiliza como la puerta de enlace predeterminada.

## ¿Qué es IPv6?

La IPv6 nació para resolver la limitación de 4.000 millones de IP públicas de IPv4. Aunque 4.000 millones de IP pueden parecer muchas, los dispositivos conectados a internet superan con creces esa cantidad. IPv6 proporciona 340 sextillones de IPs, un número extremadamente grande, para evitar los problemas que surgieron con IPv4.

### ¿Qué pasó?

En el pasado, no había tantos dispositivos conectados a internet, y las direcciones IPv4 asignadas por los proveedores de servicios de internet (ISP) eran tanto públicas como privadas. Cuando los dispositivos empezaron a superar el número de IPs disponibles, nació el NAT (Network Address Translation) para traducir las IPs públicas a privadas y viceversa. Nosotros podríamos contratar una o varias IPs públicas fijas a nuestro proveedor de internet, pero con IPv4, las cantidades serían limitadas. Sin embargo, con IPv6 podríamos tener una IP pública única para cada dispositivo, e incluso muchas más, ya que el número de direcciones disponibles es enorme, y ya no necesitaríamos la traducción del NAT.

### ¿Por qué no se usa solo IPv6?

Parece sencillo usar solo IPv6, ya que sobran direcciones, pero no lo es. Internet ya está configurado desde hace mucho tiempo y esto implica la complicación de tener que apagar todos los dispositivos, switches, routers, servidores, etc., reconfigurarlo todo y volver a ponerlo en funcionamiento. Esto es imposible, ya que no podemos dejar al mundo sin internet y desconectado de todo. Por eso, conviven ambos tipos de conexiones. Sin embargo, hay países donde la utilización de IPv6 está más avanzada que en otros. Los países que se incorporaron más tarde a internet adoptaron más esta versión. Como quedan muy pocas direcciones IPv4, la opción lógica es utilizar la versión 6.