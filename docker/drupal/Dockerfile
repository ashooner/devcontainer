FROM webdevops/php-apache-dev:7.2


#Install drush
#ENV DRUSH_VERSION 9.7.2
#RUN curl -L --silent https://github.com/drush-ops/drush/releases/download/${DRUSH_VERSION}/drush.phar \
#  > /usr/local/bin/drush && chmod +x /usr/local/bin/drush
RUN composer global require drush/drush 
RUN rm -r /var/www/html

RUN usermod -a -G root application

#get git
#RUN apt-get update && apt-get install -y git 

# install npm
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - && \
apt-get install -y nodejs
