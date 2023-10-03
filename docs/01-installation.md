---
title: Installation
---

## Requirements

Filament has a few requirements to run:

- PHP 8.1+
- Laravel v9.0+
- Livewire v2.0+

This package is compatible with other Filament v3.x products. The [form builder](/docs/forms), [table builder](/docs/tables) and [notifications](/docs/notifications) come pre-installed with the package, and no other installation steps are required to use them within a panel.

## Installation

To get started with a panel, you can install it using the commands:

```bash
composer require filament/filament:"^3.0"
php artisan filament:install --panels
```

If you don't have one, you may create a new user account using:

```bash
php artisan make:filament-user
```

Visit your app at `/admin` to sign in, and you're now ready to start [building your app](getting-started)!

## Deploying to production

By default, all `App\Models\User`s can access Filament locally. To allow them to access Filament in production, you must take a few extra steps to ensure that only the correct users have access to the app.

Please see the [Users page](users#authorizing-access-to-the-admin-panel).

If you don't complete these steps, there will be a 403 error when you try to access the app in production.

## Publishing configuration

If you wish, you may publish the configuration of the package using:

```bash
php artisan vendor:publish --tag=filament-config
```

## Publishing translations

If you wish to translate the package, you may publish the language files using:

```bash
php artisan vendor:publish --tag=filament-translations
```

Since this package depends on other Filament packages, you may wish to translate those as well:

```bash
php artisan vendor:publish --tag=filament-actions-translations
php artisan vendor:publish --tag=filament-forms-translations
php artisan vendor:publish --tag=filament-notifications-translations
php artisan vendor:publish --tag=filament-tables-translations
php artisan vendor:publish --tag=filament-support-translations
```

## Upgrading

To upgrade the package to the latest version, you must run:

```bash
composer update
php artisan filament:upgrade
```

We recommend adding the `filament:upgrade` command to your `composer.json`'s `post-autoload-dump` to run it automatically:

```json
"post-autoload-dump": [
    // ...
    "@php artisan filament:upgrade"
],
```

This should be done during the `filament:install` process, but double check it's been done.
