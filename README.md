# VestaCP---MultiPHP

1/ Các gói cần  thiết :

yum install -y gcc gcc-c++ make openssl-devel libxml2 libxml2-devel libxslt libxslt-devel libcurl-devel  bzip2-devel libjpeg-devel libpng-devel freetype-devel libicu-devel libmcrypt-devel  readline-devel 

Để làm việc với  PHP 5.3/5.4 . Nếu không sử dụng có thể bỏ qua bước này :

mkdir /usr/include/freetype2/freetype
ln -s /usr/include/freetype2/freetype.h /usr/include/freetype2/freetype/freetype.h

2/ Cài đặt và cấu hình PHPBrew

    curl -L -O https://github.com/phpbrew/phpbrew/raw/master/phpbrew
    
    chmod +x phpbrew
    
    mv phpbrew /usr/bin/phpbrew
    
    mkdir -p /usr/local/php
    
    phpbrew init --root=/usr/local/php
    
    export PHPBREW_ROOT=/usr/local/php
    
    [[ -e ~/.phpbrew/bashrc ]] && source ~/.phpbrew/bashrc

 Kiểm tra những bản PHP có thể cài đặt 
 
     phpbrew update
     
     phpbrew update --old

3/ Biên dịch PHP
 
PHP 5.3 : 

 phpbrew install 5.3.29  +default +openssl=shared -- --with-openssl-dir=/usr/include/openssl --with-mysql-sock=/var/run/mysqld/mysqld.sock --with-mysql=mysqlnd --with-mysqli=mysqlnd --enable-pdo --with-pdo-mysql=mysqlnd --enable-exif --with-jpeg-dir=/usr --with-png-dir=/usr --with-freetype-dir=/usr --with-zlib-dir=/usr --with-mcrypt=/usr --with-mhash --with-xsl=/usr --enable-zip --enable-cgi --with-curl --with-gd --enable-pcntl --enable-mbregex --enable-gd-native-ttf --with-libdir=lib64 --enable-dba=shared --enable-intl --with-readline=/usr --enable-simplexml \--enable-soap --enable-zip --with-mhash=yes --enable-shmop --enable-sockets --enable-wddx --enable-calendar --enable-sysvsem --enable-sysvshm --enable-sysvmsg --enable-bcmath --with-bz2 --enable-ctype --with-cdb --with-iconv --enable-exif --enable-ftp --with-gettext --with-pic

ln -s /usr/local/php/php/php-5.3.29/ /usr/local/php/php53

PHP 5.4 :

phpbrew install 5.4.10  +default +openssl=shared -- --with-openssl-dir=/usr/include/openssl --with-mysql-sock=/var/run/mysqld/mysqld.sock --with-mysql=mysqlnd --with-mysqli=mysqlnd --enable-pdo --with-pdo-mysql=mysqlnd --enable-exif --with-jpeg-dir=/usr --with-png-dir=/usr --with-freetype-dir=/usr --with-zlib-dir=/usr --with-mcrypt=/usr --with-mhash --with-xsl=/usr --enable-zip --enable-cgi --with-curl --with-gd --enable-pcntl --enable-mbregex --enable-gd-native-ttf --with-libdir=lib64 --enable-dba=shared --enable-intl --with-readline=/usr --enable-simplexml \--enable-soap --enable-zip --with-mhash=yes --enable-shmop --enable-sockets --enable-wddx --enable-calendar --enable-sysvsem --enable-sysvshm --enable-sysvmsg --enable-bcmath --with-bz2 --enable-ctype --with-cdb --with-iconv --enable-exif --enable-ftp --with-gettext --with-pic

 ln -s /usr/local/php/php/php-5.4.10/ /usr/local/php/php54

PHP 7.0:

phpbrew install 7.0.7  +default +openssl=shared -- --with-openssl-dir=/usr/include/openssl --with-mysql-sock=/var/run/mysqld/mysqld.sock --with-mysql=mysqlnd --with-mysqli=mysqlnd --enable-pdo --with-pdo-mysql=mysqlnd --enable-exif --with-jpeg-dir=/usr --with-png-dir=/usr --with-freetype-dir=/usr --with-zlib-dir=/usr --with-mcrypt=/usr --with-mhash --with-xsl=/usr --enable-zip --enable-cgi --with-curl --with-gd --enable-pcntl --enable-mbregex --enable-gd-native-ttf --with-libdir=lib64 --enable-dba=shared --enable-intl --with-readline=/usr --enable-simplexml \--enable-soap --enable-zip --with-mhash=yes --enable-shmop --enable-sockets --enable-wddx --enable-calendar --enable-sysvsem --enable-sysvshm --enable-sysvmsg --enable-bcmath --with-bz2 --enable-ctype --with-cdb --with-iconv --enable-exif --enable-ftp --with-gettext --with-pic

 ln -s /usr/local/php/php/php-7.0.7/ /usr/local/php/php70

PHP 7.1 :

phpbrew install 7.1.13  +default +openssl=shared -- --with-openssl-dir=/usr/include/openssl --with-mysql-sock=/var/run/mysqld/mysqld.sock --with-mysql=mysqlnd --with-mysqli=mysqlnd --enable-pdo --with-pdo-mysql=mysqlnd --enable-exif --with-jpeg-dir=/usr --with-png-dir=/usr --with-freetype-dir=/usr --with-zlib-dir=/usr --with-mcrypt=/usr --with-mhash --with-xsl=/usr --enable-zip --enable-cgi --with-curl --with-gd --enable-pcntl --enable-mbregex --enable-gd-native-ttf --with-libdir=lib64 --enable-dba=shared --enable-intl --with-readline=/usr --enable-simplexml \--enable-soap --enable-zip --with-mhash=yes --enable-shmop --enable-sockets --enable-wddx --enable-calendar --enable-sysvsem --enable-sysvshm --enable-sysvmsg --enable-bcmath --with-bz2 --enable-ctype --with-cdb --with-iconv --enable-exif --enable-ftp --with-gettext --with-pic

ln -s /usr/local/php/php/php-7.1.13/ /usr/local/php/php71

4/ Tạo templates cho vestacp

PHP 5.3 : 

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php53.sh  -O /usr/local/vesta/data/templates/web/httpd/php53.sh 

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php.tpl  -O /usr/local/vesta/data/templates/web/httpd/php53.tpl

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php.stpl   -O /usr/local/vesta/data/templates/web/httpd/php53.stpl

PHP 5.4 : 

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php54.sh  -O /usr/local/vesta/data/templates/web/httpd/php54.sh 

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php.tpl  -O /usr/local/vesta/data/templates/web/httpd/php54.tpl

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php.stpl   -O /usr/local/vesta/data/templates/web/httpd/php54.stpl

PHP 7.0:

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php70.sh -O /usr/local/vesta/data/templates/web/httpd/php70.sh 

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php.tpl  -O /usr/local/vesta/data/templates/web/httpd/php70.tpl

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php.stpl   -O /usr/local/vesta/data/templates/web/httpd/php70.stpl
 
PHP 7.1 : 

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php71.sh  -O /usr/local/vesta/data/templates/web/httpd/php71.sh

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php.tpl  -O /usr/local/vesta/data/templates/web/httpd/php71.tpl

wget https://raw.githubusercontent.com/tanhattan0051/VestaCP---MultiPHP/master/php.stpl   -O /usr/local/vesta/data/templates/web/httpd/php71.stpl


Cập nhật quyền cho các PHP :

 chmod 755 /usr/local/vesta/data/templates/web/httpd/*


