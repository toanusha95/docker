FROM ubuntu
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get install apache2 -y
RUN apt-get install apache2-utils -y
RUN apt install mysql-server -y
RUN apt install php libapache2-mod-php php-mysql -y
RUN php -v
RUN apt-get clean
RUN mkdir -p /var/www/apache/html
RUN chown -R $USER:$USER /var/www/apache/html
COPY ./index.html /var/www/apache/html/
COPY ./apache.conf /etc/apache2/sites-available/
COPY ./servername.conf /etc/apache2/conf-available/
COPY ./info.php /var/www/apache/
COPY ./dir.conf /etc/apache2/mods-enabled/
RUN a2ensite apache.conf
RUN a2dissite 000-default.conf
EXPOSE 8080
CMD ["apache2ctl","-D","FOREGROUND"]
