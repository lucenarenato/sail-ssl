# 🚢 Sail-SSL | Laravel 7 e php7.2

![Version](https://img.shields.io/github/v/release/lucenarenato/sail-ssl)
![Downloads](https://img.shields.io/packagist/dt/lucenarenato/sail-ssl)
![License](https://img.shields.io/github/license/lucenarenato/sail-ssl)
![Test](https://img.shields.io/github/actions/workflow/status/lucenarenato/sail-ssl/laravel.yml?branch=main&label=test)

 Laravel 7 e php7.2 - Laravel Sail plugin to enable SSL (HTTPS) connection with Nginx.

## Install
You need to setup [Laravel Sail](https://github.com/laravel/sail) environment before using the plugin.

### With local PHP / Composer:
```sh
composer require lucenarenato/sail-ssl --dev
php artisan sail-ssl:install
./vendor/bin/sail up
```

### With Sail container:
```sh
./vendor/bin/sail up -d
./vendor/bin/sail composer require lucenarenato/sail-ssl --dev
./vendor/bin/sail artisan sail-ssl:install
./vendor/bin/sail down
./vendor/bin/sail up
```

After containers started, you can access https://localhost.

## Environment variables
- `SERVER_NAME`
  - Determine `server_name` directive in nginx.conf
  - Default: `localhost`
- `APP_SERVICE`
  - Specify Laravel container name in docker-compose.yml
  - Default: `laravel.test`
- `HTTP_PORT`
  - Port to forward Nginx HTTP port
  - By default, request for this port would redirect to `SSL_PORT`
  - Default: `8000`
- `SSL_PORT`
  - Port to forward Nginx HTTPS port
  - Default: `443`

## Configure Nginx
`./nginx/templates/default.conf.template` will be published.
```sh
php artisan sail-ssl:publish
```

## Contribution
Feel free to create a PR!
