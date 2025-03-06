# Lámpara Wiz squire esphome
Modificación de lámpara led de doble zona.
La lámpara squire de la marca Wiz es una lámpara con 2 zonas independientes que puedes controlar con un botón, con la aplicación oficial y con Home assistant. 

El problema viene porque que la integración de que ofrecen para Home assistant no es capaz de alcanzar todas las funciones de la lámpara, no tiene independecia de zonas, no tiene efectos y marca siempre un consumo de 0W, eso si, en la información del dispositivo te da indicios de que está gobernado por algún tipo de esp.

Las soluciónes para poder tener todas las funcionalidades en el caso de ser un esp del tipo que sea son muchas, wled, tasmota, ..., pero siempre habrá que cambiar el firmware ya que es un producto con unos años y Wiz no te va a hacer un código para ese modelo, usaré esphome.
Aquí vino el problema y es que al conectar el esp32 leer los datos con esptool muestra todos los datos del micro sin problemas, descargas un .bin generado como copia de seguridad del firmware original y al subir el código de esphome te dice que está protegido, bueno, recupero con el .bin descargado pero ya está totalmente bloqueado y no te permite hacer nada.

# Operarar
Hay que empezar abriendo la lámpara y encontraremos la placa con toda la parte inferior de leds y en mi caso con un esp32-solo-1, al lado derecho del esp32 están claramente marcados sus pines de programación que realmente no servirán de nada si subes el código a otro esp32 antes de soldarselo, muchos modelos valen, yo usé un esp32-wroom por tenerlo a mano. Se prepara todo bien y se quita el esp32-solo-1 original montando un esp32 nuevo, puede programarse antes o después de la instalación. Se usan 11 pines GPIO para todo por lo que es el momento de añadir dispositivos que le permitan más funciones si te interesa.

# Importante
Hay que modificar las XXX el la configuración de ip estática o ponerla automática si se prefiere y generar los !secret o poner sus códigos generados en esphome.
