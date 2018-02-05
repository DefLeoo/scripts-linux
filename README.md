echo 'Atualizando Ubunto 16.04'

   sudo apt-get update
   sudo apt-get upgrade
   sudo apt-get dist-upgrade

 echo 'Instalar o Servidor Web Apache'

    sudo apt-get install apache2 apache2-utils

echo 'Status do servidor'
   
   systemctl status apache2

echo 'Restart servidor'
   
   sudo systemctl start apache2

echo 'Ativar servidor'
  
  sudo systemctl enable apache2 

echo 'Ver versão'
  
  apache2 -v

echo 'Endereço de ip publico'
  
  sudo apt-get install curl

echo 'Finalmente, precisamos criar o www-data (usuário Apache) como o proprietário do diretório raiz da web:'   

  sudo chown www-data /var/www/html/ -R   

echo 'Instalar mariaDB'
  
  sudo apt-get install mariadb-server mariadb-client

echo 'status'
  
  systemctl status mysql

echo 'Iniciando mariaDB'
   
  sudo systemctl start mysql

echo 'iniciar modo automatico'
  
  sudo systemctl enable mysql

echo 'Configurando root e senha'
   
   sudo mysql_secure_installation

echo 'Instalar PHP 7'

   sudo apt-get install php7.0-fpm php7.0-mysql php7.0-common php7.0-gd php7.0-json php7.0-cli php7.0-curl libapache2-mod-php7.0

echo 'Ative o módulo Apache php7.0'
   
   sudo a2enmod php7.0

echo 'Reiniciando servidor apache2'
  
  sudo systemctl restart apache2

echo 'Versão PHP'
  
  php –version

echo 'Testando servidor apache'

   sudo nano /var/www/html/test.php  

echo 'Cole este arquivo '

   <?php phpinfo(); ?>  

echo 'rode no servidor tudo ok'

echo 'Instalar phpmyadmin'
  
  sudo apt-get update
  sudo apt-get install phpmyadmin php-mbstring php-gettext
  sudo phpenmod mcrypt
  sudo phpenmod mbstring
  sudo systemctl restart apache2


//CONFIGURANDO SENHA E USUÁRIO MARIADB

   sudo mysql -u root -p
   >use mysql
   >select user, plugin from user;
   >update user set plugin='' where user='root';
   >select user, plugin from user;
   >flush privileges;
   >quit;

//LEMBRETE 
  
  tem que da permisão a pasta www
  /var/ sudo chmod 777 -R www
