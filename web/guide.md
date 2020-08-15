- Requirment php and extensions:
+ PHP 7.2
+ extensions: mongodb.so

- Set parameters:
parameters:
    database_host: 127.0.0.1
    database_port: 3306
    database_name: cocorico3
    database_user: root
    database_password: 123456
    mongodb_server: 'mongodb://localhost:27017'
    mongodb_database_name: cocorico_dev
    mailer_transport: smtp
    mailer_host: localhost
    mailer_user: null
    mailer_password: null
    mailer_port: null
    secret: d69958a4fff6ba8f0f4fc4fc2657366ccf9dd0f3
    use_assetic_controller: false
    cocorico.assets_base_urls: 'http://localhost:8000'
    router.request_context.host: 'localhost:8000'

- Install by composer:
/Applications/MAMP/bin/php/php7.2.22/bin/php composer.phar install --ignore-platform-reqs

- Init MySql database:
chmod 744 bin/init-db
./bin/init-db php --env=dev

- Init MongoDb database:
chmod 744 bin/init-mongodb
./bin/init-mongodb php --env=dev

- Remove " ->orderBy('l.createdAt', 'DESC') " at file ListingRepository.php - line 263

- Dump Assets:
/Applications/MAMP/bin/php/php7.2.22/bin/php bin/console assets:install --symlink web --env=dev
/Applications/MAMP/bin/php/php7.2.22/bin/php bin/console assetic:dump --env=dev

- Install CK Editor
/Applications/MAMP/bin/php/php7.2.22/bin/php bin/console ckeditor:install

- Change web/.htaccess.dist -> web/.htaccess

- Start server: symfony server:start

