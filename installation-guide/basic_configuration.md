# Collejo 
## Installation Documentation
### Basic Configuration

#### Directory Permissions

After installing Collejo, you may need to configure some permissions. Directories within the storage and the bootstrap/cache directories should be writable by your web server. If you are using the Homestead virtual machine, these permissions should already be set.

#### Application Key

The next thing you should do after installing Collejo is set your application key to a random string. If you installed Collejo via Composer, this key has already been set for you by the key:generate command. Typically, this string should be 32 characters long. The key can be set in the .env environment file. If you have not renamed the .env.example file to .env, you should do that now. If the application key is not set, your user sessions and other encrypted data will not be secure!

#### Database

You need to define credentials to your mysql server on the .env file located on the site root. Please note that you will need to manually create the database on server prerior to running the database migrations. Collejo cannot create a database automatically.

````
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=collejo
DB_USERNAME=homestead
DB_PASSWORD=secret
````

#### Migrations

After setting up database credentials run database migrations using the following artisan command.

```php artisan migrate```

#### Building scripts and styles

After a fresh installation or an update, or any new modules installation it is recommended that you build/re-build the scripts and styles. To do this run `npm run prod` on production environment. On development environment you could simply run `npm run watch` to listne for changes in the code.

##### Pretty URLs

###### Apache

The framework ships with a public/.htaccess file that is used to allow URLs without index.php. If you use Apache to serve your Collejo application, be sure to enable the mod_rewrite module.

If the .htaccess file that ships with Collejo does not work with your Apache installation, try this one:

```
Options +FollowSymLinks
RewriteEngine On

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ index.php [L]
```


###### Nginx

On Nginx, the following directive in your site configuration will allow "pretty" URLs:

```
location / {
    try_files $uri $uri/ /index.php?$query_string;
}
```

Of course, when using Homestead, pretty URLs will be configured automatically.

#### Configuration Caching

To give your application a speed boost, you should cache all of your configuration files into a single file using the config:cache Artisan command. This will combine all of the configuration options for your application into a single file which can be loaded quickly by the framework.

You should typically run the `php artisan config:cache` command as part of your production deployment routine. The command should not be run during local development as configuration options will frequently need to be changed during the course of your application's development.

