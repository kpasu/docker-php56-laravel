FROM centos:7.4.1708

RUN yum update -y
RUN yum install -y less wget zip unzip git

RUN yum install -y epel-release

# gulp
RUN yum install -y nodejs libnotify
RUN npm install --g gulp-cli
# cd laravel install dir
# RUN npm install

# etc
RUN yum clean all
RUN /bin/cp -f /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

WORKDIR /var/www
ENTRYPOINT ["gulp"]
CMD ["-h"]
