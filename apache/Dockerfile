FROM ubuntu

RUN apt-get update && apt-get install -y apache2 \
	vim

RUN a2enmod proxy_fcgi

# Enabling mod_rewrite
RUN a2enmod rewrite

EXPOSE 80

# On donne les droits au user www-data pour les sources dans le container
# Sans ça, on a des "permission denied" pour certains fichiers/répertoires
RUN chmod -R 771 /var/www

# On démarre le server apache
CMD /usr/sbin/apache2ctl -D FOREGROUND