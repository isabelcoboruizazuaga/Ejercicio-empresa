# EJERCICIO EMPRESA
* ## *Redes*
* ### Primera red (198.168.1.0)
    La primera red es donde están alojados el equipo de administración, recursos humanos y el director de la empresa, todos los equipos tienen IP fija y está dividida en dos subredes tal que:
 
  Máscara | Dirección de red | Primera IP | Última IP | Broadcast
  ------- | ---------------- | ---------- | --------- | ---------
  255.255.255.128 | 192.168.1.0 | 192.168.1.1 | 192.168.1.126 | 192.168.1.127
  255.255.255.224 | 192.168.1.128 | 192.168.1.129 | 192.168.1.158 | 192.168.1.159
  --------------------------------------
   * #### Primera subred
       Es la red de administración, puede alojar hasta 100 hosts. El ordenador del director tiene la IP 198.168.1.2, y es el único que puede salir al exterior. Los demás ordenadores de esa red sólo pueden comunicarse con el director.
   * #### Segunda subred 
       Es la red de recursos humanos, ésta no se comunica con ningún otro equipo, ni con el director de la empresa. Puede alojar hasta 30 hosts.
* ### Segunda red (198.168.2.0)
    Esta es la red de producción, tiene un DHCP alojado en la dirección 192.168.2.2 que proporciona direcciones IP al resto de hosts de la red (por ahora hay 4, pero puede haber más), así como les proporciona la dirección del router para que puedan salir fuera.
* ### Tercera red (198.168.3.0)
    Es la red de contabilidad, hay 4 equipos con IP fijas conectados entre sí, éstos también pueden salir fuera.
* ###  Cuarta red (198.168.4.0)
    Esta red corresponde a la de marketing. En ella se aloja un DHCP (198.168.4.2) que proporciona la dirección IP a los demás host de la red, una servidor de páginas web(198.168.4.4) en el que se encuentran los productos publicitarios y un DNS (198.168.4.3) que resuelve las dirección del servidor web. Todos los ordenadores de la segunda y tercera red tienen acceso a este DNS, es decir, tienen acceso a la web de marketing.
* ### Quinta red (198.168.5.0)
    Se trata de la red de la tienda o negocio físico. Ésta posee un sevidor DHCP (198.168.5.2) que proporciona las direcciones IP a los dispositivos conectados a la red, los cuales lo hacen mediante un punto de acceso.
* ### Sexta red (198.168.6.0)
    La sexta red es la red que hay en los almacenes. Ésta posee un servidor web (198.168.6.3) en donde se encuentra la web que permite hacer pedidos y ver los productos, un servidor DNS (198.168.6.2) que resuelve la dirección de dicha web, y un solo dispositivo con IP fija en 198.168.6.4.
* ## *Routers*
    Cada red posee su propio router que conecta dicha red con el resto de redes para permitir la comunicación entre éstas. Los únicos dispositivos que no podrán conectarse al resto de redes son los de la subred de Recursos Humanos (cuyos hosts sólo pueden comunicarse entre ellos) y los de Administración (cuyos dispositivos sólo podrán comunicarse con el Director). El ordenador del Director es el único de la primera red que podrá salir fuera. 
    Los routers a su vez conforman redes de comunicación entre ellas, de forma que las direcciones IP de estos quedan tal que:
    
  Router| IP de red (Ethernet) | IP de red (Serial1) | IP de red (Serial2) | IP de red (Serial3)
  ------- | ---------------- | ---------- | --------- | ---------
  Router1 | 192.168.1.1 | 192.168.13.1 | 192.168.14.1 | 
  Producción | 192.168.2.1 | 192.168.12.1 |   |  
  Contabilidad | 192.168.3.1 | 192.168.12.2 | 192.168.13.2 | 192.168.11.1
  Marketing | 192.168.4.1 | 192.168.11.2 |   |  
  Tienda | 192.168.5.1 | 192.168.10.1 | 192.168.14.2 |  
  Almacén | 192.168.6.1 | 192.168.10.2 |   |  
  --------------------------------------
* ## *Servidores*
    Hay dos servidores web en la empresa, el primero para los anuncios de Marketing, el cual contiene las páginas de los anuncios acabados, y uno para los productos que tiene disponibles el almacén para comprarlos.   
    
    El primero se encuentra en la dirección IP 198.168.4.4 (Red 4) y el DNS que resuelve su dirección web posee la IP 198.168.4.3. Para acceder a esta página web debe buscarse en los navegadores de la 2ª, 3ª y 4ª red la dirección www.finalizados.es (ésta mostrará un índice de los anuncios finalizados que llevará a la imagen de dicho anuncio).   
    
    El segundo se encuentra en la dirección IP 198.168.6.3 (Red 6) y su DNS en 198.168.6.2. Para acceder a esta web debe ser desde las redes 5ª y 7ª buscando www.almacen.com (esta página mostrará un índice de los productos disponibles con sus características y fotos)
