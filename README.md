# Laravel 5 Themes

+ Installation
+ Usage
 + Get All Themes
 + Set Active Theme
 + Get Current Theme
 + Check Theme
 + Set Themes Path
 + Get Themes Path
 + Get Theme's Path
 + Get Theme's View
 + Get Theme's Lang
 + Get Theme's Config
+ Artisan Commands
 + theme:make
 + theme:list
 + theme:cache
 + theme:publish

## Installation

Open your composer.json file, and add the new required package with: 

    "lchoate/themes": "~2.0"
    
Next, open a terminal and run: 

    composer update

Next, Add new service provider in config/app.php.

    'Pingpong\Themes\ThemesServiceProvider',

Next, Add new aliases in config/app.php.

    'Theme' => 'Pingpong\Themes\ThemeFacade',

Next, publish the package's assets.

    php artisan vendor:publish
    
*Now you're done.*


## Usage

### Get all themes.

    Theme::all();

Set theme active.

    Theme::set('default');
    Theme::setCurrent('default');

Get current theme active.

    Theme::getCurrent();

Check theme.

    Theme::has('simple')
    Theme::exists('other-theme');

Set theme path.

    $path = public_path('themes');
    Theme::setPath($path);

Get theme path.
    
    Theme::getThemePath('default');

Get themes path.

    Theme::getPath();

Get view from current active theme.

    Theme::view('index');
    Theme::view('folders.view');

Get translation value from active theme.

    Theme::lang('group.name');

Get theme's config value from active theme.

You can set theme related variables in the theme config file. You'll find a var for both the public path and an asset path
Setting a key/value. (note that as of v2 the config file doesn't pick up your theme's name, so you could end up interrogating the wrong theme)
    
    [
        'key' => 'value',
        'another_key' => [
            'subkey' => 'value',
            ],
        'public_path'   => '/themes/default/',
        'asset_path'    => '/themes/default/',
    ]

To read the configurations values from your theme file:

    Theme::config('key'); 
    Theme::config('another_key.subkey');
    Theme::config('another_key.subkey','Set a default value if you want');
    

You can also get config value from other theme.

// current theme
    
    Theme::config('key');

// from other theme
    
    Theme::config('bootstrap::key');

## Artisan Commands

Generate a new theme.

    php artisan theme:make foo

Show all available themes.

    php artisan theme:list

Cache all themes.

    php artisan theme:cache

Publish all theme's assets from all themes.

    php artisan theme:publish

Publish all theme's assets from the specified theme.

    php artisan theme:publish theme-name
