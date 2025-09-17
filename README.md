[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/atj4me/ddev-laravel-starter/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/atj4me/ddev-laravel-starter/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/atj4me/ddev-laravel-starter)](https://github.com/atj4me/ddev-laravel-starter/commits)
[![release](https://img.shields.io/github/v/release/atj4me/ddev-laravel-starter)](https://github.com/atj4me/ddev-laravel-starter/releases/latest)

# DDEV Laravel Starter

## Overview

This add-on integrates a Laravel-optimized configuration into your [DDEV](https://ddev.com/) project, providing a pre-configured development environment specifically tailored for Laravel applications.

## Installation

```bash
ddev add-on get atj4me/ddev-laravel-starter
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

After installation, your DDEV environment will be automatically configured with Laravel-specific optimizations:

- **PHP 8.4** - Latest PHP version for modern Laravel development
- **MariaDB 10.11** - Stable and performant database
- **Nginx-FPM** - High-performance web server configuration
- **Composer 2** - Latest dependency manager
- **Laravel optimization hook** - Automatically runs `php artisan optimize` on container start

| Command | Description |
| ------- | ----------- |
| `ddev describe` | View service status and used ports |
| `ddev logs -s web` | Check web container logs |
| `ddev exec php artisan optimize` | Manually run Laravel optimization |

## Configuration Details

The add-on applies the following DDEV configuration:

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

## Credits

**Contributed and maintained by [atj4me](https://github.com/atj4me)**
