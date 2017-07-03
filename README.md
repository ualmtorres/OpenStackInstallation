# Archivos de configuración de OpenStack Ocata

_(En progreso)_

Archivos de configuración originales y modificados para la instalación de estos componentes de OpenStack Ocata:

* Keystone
* Glance
* Nova compute
* Neutron
* Horizon
* Cinder
* Heat

Además, se propocionan los archivos de configuración:

* `/etc/hosts`
* `/etc/network/interfaces`
* `/etc/apache2/apache2.conf`
* `/etc/chrony/chrony.conf` (NTP)
* Memcached
* MariaDB

---
**NOTA**

Utilizaremos para Neutron la opcion 2: _Self-service networks_

---

## Archivos modificados por la instalación de OpenStack

### Nodo de control

| Archivo                                                   | Entorno | Keystone | Glance | Nova | Neutron | Horizon | Cinder | Heat | Barbican | Magnum | Trove |
| ----------------------------------------------------------| :-----: | :------: | :----: | :--: | :-----: | :-----: | :----: | :--: | :------: | :----: | :---: |
| `/etc/network/interfaces`                                 | X       |          |        |      |         |         |        |      |          |        |       |
| `/etc/hosts`                                              | X       |          |        |      |         |         |        |      |          |        |       |
| `/etc/chrony/chrony.conf`                                 | X       |          |        |      |         |         |        |      |          |        |       |
| `/etc/memcached.conf`                                     | X       |          |        |      |         |         |        |      |          |        |       |
| `/etc/mysql/mariadb.conf.d/99-openstack.cnf`              | X       |          |        |      |         |         |        |      |          |        |       |
| `/etc/keystone/keystone.conf`                             |         | X        |        |      |         |         |        |      |          |        |       |
| `/etc/apache2/apache2.conf`                               |         | X        |        |      |         |         |        |      |          |        |       |
| `/etc/keystone/keystone-paste.ini`                        |         | X        |        |      |         |         |        |      |          |        |       |
| Archivos de credenciales (`openrc-admin` y `openrc-demo`) |         | X        |        |      |         |         |        |      |          |        |       |
| `/etc/glance/glance-api.conf`                             |         |          | X      |      |         |         |        |      |          |        |       |
| `/etc/glance/glance-registry.conf`                        |         |          | X      |      |         |         |        |      |          |        |       |
| `/etc/nova/nova.conf`                                     |         |          |        | X    | X       |         | X      |      |          |        |       |
| `/etc/neutron/neutron.conf`                               |         |          |        |      | X       |         |        |      |          |        |       |
| `/etc/neutron/plugins/ml2/ml2_conf.ini`                   |         |          |        |      | X       |         |        |      |          |        |       |
| `/etc/neutron/plugins/ml2/linuxbridge_agent.ini`          |         |          |        |      | X       |         |        |      |          |        |       |
| `/etc/neutron/l3_agent.ini`                               |         |          |        |      | X       |         |        |      |          |        |       |
| `/etc/neutron/dhcp_agent.ini`                             |         |          |        |      | X       |         |        |      |          |        |       |
| `/etc/neutron/metadata_agent.ini`                         |         |          |        |      | X       |         |        |      |          |        |       |
| `/etc/openstack-dashboard/local_settings.py`              |         |          |        |      |         | X       |        |      |          |        |       |
| `/etc/cinder/cinder.conf`                                 |         |          |        |      |         |         | X      |      |          |        |       |
| `/etc/heat/heat.conf`                                     |         |          |        |      |         |         |        | X    |          |        |       |
| `/etc/barbican/barbican.conf`                             |         |          |        |      |         |         |        |      | X        |        |       |
| `/etc/barbican/barbican-api-paste.ini`                    |         |          |        |      |         |         |        |      | X        |        |       |
| `/etc/magnum/magnum.conf`                                 |         |          |        |      |         |         |        |      |          | X      |       |
| `/etc/trove/trove.conf`                                   |         |          |        |      |         |         |        |      |          |        | X     |
| `/etc/trove/trove-taskmanager.conf`                       |         |          |        |      |         |         |        |      |          |        | X     |
| `/etc/trove/trove-conductor.conf`                         |         |          |        |      |         |         |        |      |          |        | X     |


### Nodo de cómputo

| Archivo                                                           | Entorno | Nova | Neutron |
| ------------------------------------------------------------------| :-----: | :--: | :-----: |
| `/etc/network/interfaces`                                         | X       |      |         |
| `/etc/hosts`                                                      | X       |      |         |
| `/etc/chrony/chrony.conf`                                         | X       |      |         |
| `/etc/nova/nova.conf`                                             |         | X    | X       |
| `/etc/neutron/neutron.conf`                                       |         |      | X       |
| `/etc/neutron/plugins/ml2/linuxbridge_agent.ini`                  |         |      | X       |

### Nodo de almacenamiento de bloques

| Archivo                                                           | Entorno | Cinder |
| ------------------------------------------------------------------| :-----: | :----: |
| `/etc/lvm/lvm.conf`                                               | X       | X      |
| `/etc/cinder/cinder.conf`                                         | X       | X      |

## Configuración utilizada para la modificación

**Nodo de control**

IP: 10.0.0.18
Gateway: 10.0.0.1

**Nodo de cómputo**

IP: 10.0.0.17
Gateway: 10.0.0.1

Los archivos de configuración están organizados en carpetas `controller` y `compute` y son los correspondientes a los nodos de control y cómputo, respectivamente.
