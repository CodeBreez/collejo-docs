# Collejo 
## Installation Documentation
### Server Requirements

Since Collejo is written on the Laravel framework, it requires the same system requirements Laravel requires. Of course, all of these requirements are satisfied by the Laravel Homestead virtual machine, so it's highly recommended that you use [Homestead](https://laravel.com/docs/5.1/homestead) for your local Collejo installation environment.

However, if you are not using Homestead, you will need to make sure your server meets the following basic requirements:

- PHP >= 7.1.3
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension
- Ctype PHP Extension
- JSON PHP Extension
- MySQL 5.6 or newer

##### Optional Recommend Requirements:

We highly recommend using [redis](http://redis.io/) for caching, session handling and queues.
