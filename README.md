# phat-reaction-googlefonts-cache
New cache for http://phat-reaction.com/googlefonts.php?format=php

# History
Someone made a list of all google fonts a couple years ago, but the site was removed from the internet. The problem is that a lot of people rely on his list and probably got this warning/error:
```
Warning: file_get_contents(http://phat-reaction.com/googlefonts.php?format=php): failed to open stream: php_network_getaddresses: getaddrinfo failed
```
So from http://web.archive.org/ I retrived the list and put it on github.

# How to fix it
In your php codebase there's probably this line:
```php
$fontsSerialized = file_get_contents('http://phat-reaction.com/googlefonts.php?format=php');
```
So you just need to change the url with this one: https://raw.githubusercontent.com/gabrielsanterre/phat-reaction-googlefonts-cache/master/google-fonts-list-serialized-php.txt
```php
$fontsSerialized = file_get_contents('https://raw.githubusercontent.com/gabrielsanterre/phat-reaction-googlefonts-cache/master/google-fonts-list-serialized-php.txt');
```
Or you can save the file on your own server so this error won't happen again
