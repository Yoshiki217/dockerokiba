FROM httpd:2.4.54

RUN apt-get update && apt-get install -y \
  php7.4 \
  libphp7.4-embed \
  php7.4-mbstring \
  php7.4-xml
RUN ln -s /usr/lib/apache2/modules/libphp7.4.so /usr/local/apache2/modules/libphp7.4.so

COPY ./html /usr/local/apache2/htdocs/
# COPY ./httpd.conf /usr/local/apache2/conf/
CMD httpd -D FOREGROUND
