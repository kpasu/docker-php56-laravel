FROM centos:7.4.1708

RUN yum update -y
RUN yum install -y less wget zip unzip git

RUN yum install -y epel-release
RUN rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm

RUN yum install -y httpd
RUN yum install -y redis

# php
RUN yum install --enablerepo=remi,remi-php56 -y install php php-cli php-devel php-common php-mbstring php-mysql php-phpunit-PHPUnit php-pecl-xdebug php-fpm php-gd php-gmp php-mcrypt php-opcache php-pdo php-xml php-zip

# composer
WORKDIR /tmp
RUN curl -sS https://getcomposer.org/installer | php
RUN mv ./composer.phar /usr/local/bin/composer
RUN composer global require "laravel/installer"
ENV PATH $PATH:/root/.composer/vendor/bin

# gulp
RUN yum install -y nodejs libnotify
RUN npm install --g gulp-cli
# cd laravel install dir
# RUN npm install

#chef
WORKDIR /tmp
RUN curl -LO https://packages.chef.io/files/stable/chefdk/2.4.17/el/7/chefdk-2.4.17-1.el7.x86_64.rpm
RUN rpm -Uvh chefdk-2.4.17-1.el7.x86_64.rpm

# etc
RUN yum clean all
ENV TZ="Asia/Tokyo"

WORKDIR /var/www
ENTRYPOINT ["chef"]
CMD ["-h"]
