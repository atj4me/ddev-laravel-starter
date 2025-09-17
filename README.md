# DDEV Laravel Starter

[![tests](https://github.com/atj4me/ddev-laravel-starter/actions/workflows/tests.yml/badge.svg)](https://github.com/atj4me/ddev-laravel-starter/actions/workflows/tests.yml)

A DDEV add-on that provides an optimized Laravel development environment configuration.

## What does this add-on do?

This add-on configures your DDEV environment with Laravel-specific optimizations:

- **PHP 8.4** - Latest PHP version for modern Laravel development
- **MariaDB 10.11** - Stable and performant database
- **Nginx-FPM** - High-performance web server configuration
- **Composer 2** - Latest dependency manager
- **Laravel optimization hook** - Automatically runs `php artisan optimize` on container start

## Installation

```bash
ddev add-on get atj4me/ddev-laravel-starter
```

## Usage

After installation, the add-on will configure your DDEV environment with Laravel-optimized settings. The configuration will be applied automatically when you start your DDEV project.

## Configuration Details

The add-on applies the following configuration:

```yaml
type: laravel
docroot: public
php_version: "8.4"
webserver_type: nginx-fpm
xdebug_enabled: false
database:
  type: mariadb
  version: "10.11"
use_dns_when_possible: true
composer_version: "2"
corepack_enable: false
performance_mode: "none"
bind_all_interfaces: false
hooks:
  post-start:
    - exec: 'php artisan optimize'
```

## Requirements

- DDEV v1.24.3 or higher
- A Laravel project (or a project where you plan to install Laravel)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Credits

**Contributed and maintained by [atj4me](https://github.com/atj4me)**
