# Serve

The `php artisan serve` command from Laravel is not available in Lumen, so you will need to add it manually.

## Command

You need to add an artisan command to launch the server.  Run the following command to copy the ServeCommand class into your application.

```
curl -o app/Console/Commands/ServeCommand.php https://raw.githubusercontent.com/matthew-james/lumen-recipes/master/ServeCommand.php
```

## Server

The ServeCommand uses the built in webserver, but expects a file called `server.php` to exist in the base path.  The following command will copy this file from the full Laravel framework.

```
curl -o server.php https://raw.githubusercontent.com/laravel/laravel/v5.2.0/server.php
```

## Registration

Next you need to register the Command with your application.  The ServeCommand class name should be added to `app/Console/Kernel.php`.

```php
protected $commands = [
  // your other commands...
  Commands\ServeCommand::class
];
```
