#  Configuração do (webservers2) e virtualhost test.dev
sudo apt-get update && sudo apt-get upgrade -y

## -Instalar apache2
sudo apt-get install apache2 -y

### -Criar directório test.dev
sudo mkdir /var/www/html/test.dev

### -Definir permissões
sudo chown -R $USER:$USER /var/www/html/test.dev && sudo chmod -R 755 /var/www

### -Criar index.html
sudo vim /var/www/html/test.dev/index.html

### -Criar um VirtualHost que aponte para test.dev
sudo nano /etc/apache2/sites-available/test.dev.conf

## Restart no apache2
sudo apache2ctl configtest
sudo a2ensite test.dev.conf
 /etc/init.d/apache2 restart

