FROM centos:7.4.1708

RUN yum update -y
RUN yum install -y git unzip

WORKDIR /tmp
RUN curl -LO https://packages.chef.io/files/stable/chefdk/2.4.17/el/7/chefdk-2.4.17-1.el7.x86_64.rpm
RUN rpm -Uvh chefdk-2.4.17-1.el7.x86_64.rpm

RUN yum install -y httpd

#ENTRYPOINT ["httpd"]
#CMD ["-v"]
