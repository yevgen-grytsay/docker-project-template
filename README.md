
# Docker Project Template


## Adminer
[http://localhost:8080](http://localhost:8080)


## Known bugs PHP 7.2

* Щоб увімкнути Xdebug, треба зайти в контейнер і виконати `docker-php-ext-enable xdebug`.
  Можливо це спричинено помилкою, яка виникає в процесі інсталяції Xdebug `pecl install xdebug-2.9.8`.
  
  ```
  RUN pecl install xdebug-2.9.8 \
    && docker-php-ext-enable xdebug
  ```
  ```
  Build process completed successfully
  Installing '/usr/local/lib/php/extensions/no-debug-non-zts-20170718/xdebug.so'
  install ok: channel://pecl.php.net/xdebug-2.9.8
  configuration option "php_ini" is not set to php.ini location
  You should add "zend_extension=/usr/local/lib/php/extensions/no-debug-non-zts-20170718/xdebug.so" to php.ini
  ```
