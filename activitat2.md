# Instalació de Owncloud en Linux

## Índex

* Instal·lació de Apache
* Instal·lació MariaDB
* Creacio de base de dades
* Instal·lació de PHP i els moduls necesaris
* Instal·lació de Ownclaud


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

El primer que ens demanarà serà posar una contrasenya per a l'usuari "root" en el posaré "Admin2022@"
i ens preguntarà si volem canviar el socket d'autentificació pressionem enter, ja que és l'opcio predeterminada i li donem que sí també a canviar la contrasenya de root

![captura](

Ens preguntarà altres cises com si volem esborrar els usuaris anònims o si volem desactivar que puguin entrar en mode root de forma remota polsarem enter a tot menys al dubte del root que donarem no.

![captura](

I per últim reiniciem el MariaDB

`sudo systemctl restart mariadb.service` o també podem usar `sudo service mariadb.service restart`

![captura](

### Creacio de base de dades


El primer a fer és entrar a MariaDB i després crear la base de dades amb les següents comandes

`sudo mysql -u root -p`

![captura](

`CREATE DATABASE owncloud;`

![captura](

Després crearem un usuari que és dirà "ownclouduser" i la seva contrasenya serà "Admin2022@"

`CREATE USER 'ownclouduser'@'localhost' IDENTIFIED BY 'Admin2022@';`
![captura](

Li haurem de donar accés a la base de dades a l'usuari que acabem de crear

`GRANT ALL ON owncloud.* TO 'ownclouduser'@'localhost' IDENTIFIED BY 'Admin2022@' WITH GRANT OPTION;`

![captura](

Per últim aplicarem els canvis i sortirem

`FLUSH PRIVILEGES;`
`EXIT;`







