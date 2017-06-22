# Archivos de configuración de OpenStack Ocata

_(En progreso)_

Archivos de configuración originales y modificados para la instalación de estos componentes de OpenStack Ocata:

* Keystone
* Glance
* Nova compute
* Neutron
* Horizon

Además, se propocionan los archivos de configuración:

* `/etc/hosts`
* `/etc/network/interfaces`
* `/etc/apache2/apache2.conf`
* `/etc/chrony/chrony.conf` (NTP)
* Memcached
* MariaDB
*
## Configuración utilizada para la modificación

**Nodo de control**

IP: 10.0.0.18
Gateway: 10.0.0.1

**Nodo de cómputo**

IP: 10.0.0.17
Gateway: 10.0.0.1

Los archivos de configuración están organizados en carpetas `controller` y `compute` y son los correspondientes a los nodos de control y cómputo, respectivamente.
