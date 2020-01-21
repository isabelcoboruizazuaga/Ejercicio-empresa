# EJERCICIO EMPRESA
* ## *Redes*
* ## Primera red
    La primera red es donde están alojados el equipo de administración, recursos humanos y el director de la empresa, todos los equipos tienen IP fija y está dividida en dos subredes tal que:
 
  Máscara | Dirección de red | Primera IP | Última IP | Broadcast
  ------- | ---------------- | ---------- | --------- | ---------
  255.255.255.128 | 192.168.1.0 | 192.168.1.1 | 192.168.1.126 | 192.168.1.127
  255.255.255.224 | 192.168.1.128 | 192.168.1.129 | 192.168.1.158 | 192.168.1.159
  --------------------------------------
   * ### Primera subred
       Es la red de administración, puede alojar hasta 100 hosts. El ordenador del director tiene la IP 198.168.1.2, y es el único que puede salir al exterior. Los demás ordenadores de esa red sólo pueden comunicarse con el director.
   * ### Segunda subred
       Es la red de recursos humanos, ésta no se comunica con ningún otro equipo, ni con el director de la empresa. Puede alojar hasta 30 hosts.
* ## Segunda red
    Esta es la red de producción, tiene un DHCP alojado en la dirección 192.168.2.2 que proporciona direcciones IP al resto de hosts de la red (por ahora hay 4, pero puede haber más), así como les proporciona la dirección del router para que puedan salir fuera.
* ## Tercera red
    Es la red de contabilidad, hay 4 equipos con IP fijos conectados entre sí, éstos también pueden salir fuera.
* ##  Cuarta red

    
Las características de las tres subredes en las que está dividida están explicadas en la tabla. Cada host de la subred está comunicado por un switch, que a su vez conecta con otro switch que une las subredes.
  * ### Segunda red
