**Installation**
```
yum install php-pecl-zendopcache
```
**Note:** In PHP version 5.5 it comes with a caching engine built-in – OpCache

We can **rest OpCache** via following method's:

**1.** Width validate_timestamps disabled, you must reset the OpCache manually or restart Apache for changes to the filesystem to take effect. 
**2.** After each code deployment you can login to the Magento admin and goto the OpCache control panel and hit reset cache. 
**3.** Use the command line reset by curling a page with something like this
```
<?php
require_once('app/Mage.php');
umask(0);
Mage::app();

$result = Mage::getSingleton('opcache/cache')->reset();
if ($result === TRUE) {
    echo 'Reset cache successful!';
} else {
    echo 'Reset cache failed!';
}
?>
```

**Note:** for above to work you need this extension:
https://github.com/SchumacherFM/Magento-OpCache

