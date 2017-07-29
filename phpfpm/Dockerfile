FROM daocloud.io/php:5.6-fpm
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        curl \
        libmemcached-dev \
        libz-dev \
        libpq-dev \
        libjpeg-dev \
        libpng12-dev \
        libfreetype6-dev \
        libssl-dev

# Install the PHP pdo_mysql extention
RUN docker-php-ext-install mysqli \
    && docker-php-ext-install pdo_mysql

#####################################
# gd:
#####################################

# Install the PHP gd library
RUN docker-php-ext-configure gd \
        --with-jpeg-dir=/usr/usr/include/ \
        --with-freetype-dir=/usr/include/ && \
    docker-php-ext-install gd

##
## 用完包管理器后安排打扫卫生可以显著的减少镜像大小
RUN apt-get clean \
&& apt-get autoclean \
&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*