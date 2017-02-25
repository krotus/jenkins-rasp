# jenkins-rasp
Step by step setup and configure raspberry pi machine for continuous integration php projects.
I'm using a Minimal image based on Debian Jessie (Raspbian Jessie Lite).
You can download it from: https://www.raspberrypi.org/downloads/raspbian/

# Packages list
- Git
- Composer
- PHPUnit
- Jenkins
- PHP 7.0
- MYSQL Server
- Apache2

# step by step

Step 1 - Prepare the machine
Once you power on the raspberry pi, will start installing some packages as PHP 7.0 hasn’t yet made the official repository sources, so we need to add one which provides us with the PHP 7.0 packages. Edit your sources file with this command:
* sudo nano /etc/apt/sources.list

Below the existing entries in the file on a blank line, add the following line:
deb http://repozytorium.mati75.eu/raspbian jessie-backports main contrib non-free

Next we need to add a couple of certificates in order to allow us to use the sources with apt-get. 
Run the following two commands:
* sudo gpg --keyserver pgpkeys.mit.edu --recv-key CCD91D6111A06851
* sudo gpg --armor --export CCD91D6111A06851 | sudo apt-key add -

And finally we need to update the package list by running:
* sudo apt-get update

Step 2 – Install the core Apache2, MySQL, Git, Composer and PHP 7 packages
We’re ready to install Apache2 and PHP7, along with some common packages that we may need for most web applications.
Install these packages:
* apt-get install apache2 php7.0 php7.0-curl php7.0-gd php7.0-imap php7.0-json ph p7.0-mcrypt php7.0-mysql php7.0-opcache php7.0-xmlrpc libapache2-mod-php7.0 php-xml php-mbstring git mysql-server

Install MySQL Server (Optional)
* apt-get install -y mysql-server

Install composer
* curl -sS https://getcomposer.org/installer | php
* mv composer.phar /usr/local/bin/composer






