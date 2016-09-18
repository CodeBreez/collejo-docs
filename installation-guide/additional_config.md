# Collejo 
## Installation Documentation
### Additional Configuration

#### Configuration Files

All of the configuration files for Collejo are stored in the config directory. Each option is documented, so feel free to look through the files and get familiar with the options available to you.

Collejo needs almost no other configuration out of the box. You are free to get started! However, you may wish to review the `config/collejo.php` file and its documentation. It contains several options such as caching, default settings that you may wish to change according to your installation.

You may also want to configure a few additional components of Collejo, such as:

- Cache

....Collejo keeps most of the data cached to provide the user with a faster viewing experience. You may use `memcached`, `redis` or `mysql` as your cache driver. Note that performance may differ on different drivers.

- Database

....Currently Collejo only supports MySQL. More drivers to come...

- Session

....User sessions are stored on the database by default. You may use a different driver, such as redis. You may also configure settings such as cookie expiration time here.

- Email

....Whether you using your own SMTP server or a third party service to send email they can be configured here.

- Disks 

....Collejo stores files such as user images, reports and other attachable media on disks. If you're using services such as [s3](http://docs.aws.amazon.com/AmazonS3/latest/dev/), you may configure them there.

- Uploader

....You may configure Collejo file uploader to accept different file type. You may also state which disk to upload them to.

- Image

....Collejo resized your images using GD library. You may change it here.

- Queue

....Whether you using a third party queuing service or a self hosted worker configure them here.
