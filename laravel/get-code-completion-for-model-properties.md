# Get code completion for model properties in PhpStorm

There is no out-of-the-box code completion for model properties. They need to be annotated like this:
```
@property $name
```
To have it generated automatically, you have to:
1. Install two Composer packages:
```
composer require barryvdh/laravel-ide-helper
composer require doctrine/dbal
composer update
```
2. Add the service provider in `providers` array in `config/app.php`:
```
Barryvdh\LaravelIdeHelper\IdeHelperServiceProvider::class,
``` 
3. Run:
````
php artisan ide-helper:models
````
***(For this to work the mysql service needs to be up!)***
