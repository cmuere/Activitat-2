# Instalació de Owncloud en Linux

## Índex

* Instal·lació de Apache
* Instal·lació MariaDB
* Creacio de base de dades
* Instal·lació de PHP i els moduls necesaris
* Instal·lació de Ownclaud
* Configuracio de Apache


### Instalacio de Apache

Per a instal·lar Apache a l'Ubuntu haurem d'usar la següent comanda

`sudo apt install apache2`
![captura](

Després haurem de desactivar el llistat de directoris del servidor

`sudo sed -i "s/Options Indexes FollowSymLinks/Options FollowSymLinks/" /etc/apache2/apache2.conf`
![captura](

### Instal·lació MariaDB

Per a instal·lar el MariaDB haurem d'usar la següent comanda

`sudo apt-get install mariadb-server mariadb-client -y`
![captura](

Després d'instal·lar MariaDB haurem de configurar-la

`sudo mysql_secure_installation`
![captura](









