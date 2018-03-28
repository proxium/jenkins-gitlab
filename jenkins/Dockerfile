FROM jenkins/jenkins:lts

USER root

RUN set -ex \
   && apt-get update \
   && apt-get install -y nano \
   php7.0 \
   php7.0-xsl \
   php7.0-dom \
   php7.0-zip \
   php7.0-mbstring \
   && mkdir /var/jenkins_home/.composer/ \
   && chown -R jenkins:jenkins /var/jenkins_home/.composer/ \
   && curl -LO https://deployer.org/deployer.phar \
   && mv deployer.phar /usr/local/bin/dep \
   && chmod +x /usr/local/bin/dep

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

USER jenkins
