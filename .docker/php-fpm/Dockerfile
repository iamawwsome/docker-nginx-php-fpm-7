FROM centos:7
RUN yum update -y && \
    yum install -y epel-release

RUN yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm && \
    yum install -y yum-utils && \
    yum-config-manager --enable remi-php72 && \
    yum -y update

RUN yum install -y php-fpm php-xml php-cli php-bcmath php-dba php-gd php-intl php-mbstring php-mysql php-pdo php-soap php-pecl-apcu php-pecl-imagick

RUN useradd -M -d /opt/app -s /bin/false nginx

COPY ./.docker/php-fpm/php-fpm.conf /etc/php-fpm.conf
COPY ./.docker/php-fpm/www.conf /etc/php-fpm.d/www.conf
COPY ./.docker/php-fpm/php.ini /etc/php.ini

RUN yum clean all

CMD php-fpm