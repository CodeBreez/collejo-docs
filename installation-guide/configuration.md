# Collejo 
## Installation Documentation
### Configuration
#### Basic Configuration

All of the configuration files for Collejo are stored in the config directory. Each option is documented, so feel free to look through the files and get familiar with the options available to you.

##### Directory Permissions

After installing Collejo, you may need to configure some permissions. Directories within the storage and the bootstrap/cache directories should be writable by your web server. If you are using the Homestead virtual machine, these permissions should already be set.

##### Application Key

The next thing you should do after installing Collejo is set your application key to a random string. If you installed Collejo via Composer, this key has already been set for you by the key:generate command. Typically, this string should be 32 characters long. The key can be set in the .env environment file. If you have not renamed the .env.example file to .env, you should do that now. If the application key is not set, your user sessions and other encrypted data will not be secure!

##### Additional Configuration

Collejo needs almost no other configuration out of the box. You are free to get started! However, you may wish to review the config/app.php file and its documentation. It contains several options such as timezone and locale that you may wish to change according to your installation.

You may also want to configure a few additional components of Collejo, such as:

- Cache
- Database
- Session

Refer to the file on app/config directory for more information.


##### Pretty URLs

###### Apache

The framework ships with a public/.htaccess file that is used to allow URLs without index.php. If you use Apache to serve your Collejo application, be sure to enable the mod_rewrite module.

If the .htaccess file that ships with Collejo does not work with your Apache installation, try this one:

````Options +FollowSymLinks
RewriteEngine On

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ index.php [L]````

###### Nginx

On Nginx, the following directive in your site configuration will allow "pretty" URLs:

````location / {
    try_files $uri $uri/ /index.php?$query_string;
}````

Of course, when using Homestead, pretty URLs will be configured automatically.

#### Configuration Caching

To give your application a speed boost, you should cache all of your configuration files into a single file using the config:cache Artisan command. This will combine all of the configuration options for your application into a single file which can be loaded quickly by the framework.

You should typically run the `php artisan config:cache` command as part of your production deployment routine. The command should not be run during local development as configuration options will frequently need to be changed during the course of your application's development.