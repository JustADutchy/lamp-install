#install apache
sudo apt install apache2

#check status
sudo systemctl status apache2

#install php
sudo apt install php-curl php-gd php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip

#check php version
php --version

#restart apache2 > changes will take effect
sudo systemctl restart apache2

#delete php.info
sudo rm /var/www/html/phpinfo.php

#install mariadb
sudo apt install mariadb-server mariadb-client

#check mariadb
sudo systemctl status mariadb

#install mariadb services
sudo mysql_secure_installation

#mysql root login \\ You will be prompted for the password you set for the MySQL root account.
sudo mysql -u root -p

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'new_password';
EXIT;
mysql -u root -p

#create your first database
CREATE DATABASE wordpressdb DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;

#create wordpress user for the db
mysql > CREATE USER 'wpuser'@'%' IDENTIFIED WITH mysql_native_password BY 'password';

#grant permissions to wpuser
GRANT ALL ON wordpress.* TO 'wordpressuser'@'%';

#apply recent changes
FLUSH PRIVILEGES;

##optional 

