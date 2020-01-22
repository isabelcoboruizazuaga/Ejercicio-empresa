# EJERCICIO EMPRESA
* ## *Redes*
* ## Primera red (198.168.1.0)
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
* ## Segunda red (198.168.2.0)
    Esta es la red de producción, tiene un DHCP alojado en la dirección 192.168.2.2 que proporciona direcciones IP al resto de hosts de la red (por ahora hay 4, pero puede haber más), así como les proporciona la dirección del router para que puedan salir fuera.
* ## Tercera red (198.168.3.0)
    Es la red de contabilidad, hay 4 equipos con IP fijos conectados entre sí, éstos también pueden salir fuera.
* ##  Cuarta red (198.168.4.0)
    Esta red corresponde a la de marketing. En ella se aloja un DHCP (198.168.4.2) que proporciona la dirección IP a los demás host de la red, una servidor de páginas web(198.168.4.4) en el que se encuentran los productos publicitarios y un DNS (198.168.4.3) que resuelve las dirección del servidor web. Todos los ordenadores de la segunda y tercera red tienen acceso a este DNS, es decir, tienen acceso a la web de marketing.
* ## Quinta red (198.168.5.0)
    Se trata de la red de la tienda o negocio físico. Ésta posee un sevidor DHCP (198.168.5.2) que proporciona las direcciones IP a los dispositivos conectados a la red, los cuales lo hacen mediante un punto de acceso.
* ## Sexta red (198.168.6.0)
    La sexta red es la red que hay en los almacenes. Ésta posee un servidor web (198.168.6.3) en donde se encuentra la web que permite hacer pedidos y ver los productos, un servidor DNS (198.168.6.2) que resuelve la dirección de dicha web, y un solo dispositivo con IP fija en 198.168.6.4.
