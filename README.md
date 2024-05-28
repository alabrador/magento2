**Descargar la versión de magento 2**

```
composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition=2.4.5-p6
```

**Asignar los permisos de carpetas y sub carpetas**

```
cd /var/www/html/<magento install directory>
find var generated vendor pub/static pub/media app/etc -type f -exec chmod g+w {} +
find var generated vendor pub/static pub/media app/etc -type d -exec chmod g+ws {} +
chown -R :www-data . # Ubuntu
chmod u+x bin/magento
```

**Instalar Magento 2**
```
bin/magento setup:install --base-url=https://domain \
--db-host=172.17.0.2 \
--db-name=dosc_producciondb \
--db-user=root \
--db-password=password_db \
--admin-firstname=Alexander \
--admin-lastname=Labrador \
--admin-email=user@comain.com \
--admin-user=admin \
--admin-password=admin123 \
--language=es_ES \
--currency=EUR \
--timezone=Europe/Madrid \
--use-rewrites=1 \
--search-engine=elasticsearch7 \
--elasticsearch-host=localhost \
--elasticsearch-port=9200 \
--elasticsearch-index-prefix=magento2 \
--elasticsearch-timeout=15
```
