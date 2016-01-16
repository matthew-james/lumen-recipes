# Filesystem

The iiluminate/filesytem package is included with Lumen, but only the [Filesystem](https://github.com/illuminate/filesystem/blob/master/Filesystem.php) class is available.  You will need to register the filesystem components manually if you would like to use the disk manager, cloud storage, or the Storage facade.

## Config

The service provider expects a configuration file to exist.  The following lines will create the config directory if it does not exist and copy a fresh configuration file from the full Laravel framework.

```
mkdir -p config
curl -o config/filesystems.php https://raw.githubusercontent.com/laravel/laravel/v5.2.0/config/filesystems.php
```

## Registration

Next you need to register the service provider with your application and tell Lumen to load your config.  The following lines should be added to `bootstrap/app.php`.

```php
$app->register(Illuminate\Filesystem\FilesystemServiceProvider::class);
$app->configure('filesystems');
```

## Facade

If you would like to use the facade, make sure you have enabled facades by uncommenting the `$app->withFacades()` line in `bootstrap/app.php`.  Next, add the following code to register the Storage facade.

```php
if( ! class_exists('Storage') ) {
    class_alias(Illuminate\Support\Facades\Storage::class, 'Storage');
}
```
