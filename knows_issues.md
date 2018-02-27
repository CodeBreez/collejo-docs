# Collejo 
## Known Issues

 ### Not using redis driver for caching will cause empty database results:
 If you're using file cache driver, it might give you empty results even if you have disabled `criteria caching`. Always use redis to bypass this issue.
