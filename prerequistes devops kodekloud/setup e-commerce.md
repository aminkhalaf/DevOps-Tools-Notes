## install maria db

Run the command: sudo yum install -y mariadb-server to install

Run the command: sudo systemctl start mariadb to start the process

Run the command: sudo systemctl enable mariadb to ensure that process is started on server reboot.

## Configure Database as below

Run sudo mysql command to get into MYSQL shell then run below commands (in capital alphabets)

MariaDB > CREATE DATABASE ecomdb;

MariaDB > CREATE USER 'ecomuser'@'localhost' IDENTIFIED BY 'ecompassword';

MariaDB > GRANT ALL PRIVILEGES ON *.* TO 'ecomuser'@'localhost';

MariaDB > FLUSH PRIVILEGES;

## We have downloaded Product Inventory Information

sudo mysql < /opt/db-load-script.sql

## install some programs

sudo yum install -y httpd php php-mysqlnd

## make php page the default page for httpd

sudo sed -i 's/index.html/index.php/g' /etc/httpd/conf/httpd.conf

## Start and enable httpd

sudo systemctl start httpd ; sudo systemctl enable httpd

## Download code with git. Install git if necessary

sudo yum install -y git; sudo git clone https://github.com/kodekloudhub/learning-app-ecommerce.git /var/www/html/

## Since we have both the web and database on the same server, update the IP address configured in index.php file to localhost.
## Change 172.20.1.101 to localhost in index.php file.

sudo sed -i 's/172.20.1.101/localhost/g' /var/www/html/index.php