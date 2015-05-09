<<<<<<< HEAD
## Laravel Themes

[![Build Status](https://travis-ci.org/pingpong-labs/themes.svg?branch=master)](https://travis-ci.org/pingpong-labs/themes)
[![Latest Stable Version](https://poser.pugx.org/pingpong/themes/v/stable.svg)](https://packagist.org/packages/pingpong/themes) [![Total Downloads](https://poser.pugx.org/pingpong/themes/downloads.svg)](https://packagist.org/packages/pingpong/themes) [![Latest Unstable Version](https://poser.pugx.org/pingpong/themes/v/unstable.svg)](https://packagist.org/packages/pingpong/themes) [![License](https://poser.pugx.org/pingpong/themes/license.svg)](https://packagist.org/packages/pingpong/themes)

### Installation

Open your composer.json file, and add the new required package.
```
   "pingpong/themes": "1.0.*"
```
Next, open a terminal and run.
```
composer update
```

Next, Add new service provider in `app/config/app.php`.

```php
  'Pingpong\Themes\ThemesServiceProvider',
```

Next, Add new aliases in `app/config/app.php`.

```php
   'Theme' => 'Pingpong\Themes\Facades\Theme',
```

Next, publish the asset. The asset is an example theme.
```
php artisan asset:publish pingpong/themes
```

Done.

### Usage

Get all themes.
```php
Theme::all();
```

Set theme active.
```php
Theme::set('default');

Theme::setCurrent('default');
```

Get current theme active.
```php
Theme::getCurrent();
```

Check theme.
```php
Theme::has('simple')

Theme::exists('other-theme');
```

Set theme path.
```php
$path = public_path('themes');

Theme::setPath($path);
```

Get theme path.
```php
Theme::getThemePath('default');
```

Get themes path.
```php
Theme::getPath();
```

Get view from current active theme.
```php
Theme::view('index');

Theme::view('folders.view');
```

Get config from current active theme.
```php
Theme::config('group.name');
```

Get lang from current active theme.
```php
Theme::lang('group.name');
```

### License

This package is open-sourced software licensed under [The BSD 3-Clause License](http://opensource.org/licenses/BSD-3-Clause)
=======
Laravel Themes
==============

Official documentation is located [here](http://sky.pingpong-labs.com/docs/2.0/themes)
>>>>>>> 2.0
