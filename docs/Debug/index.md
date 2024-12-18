Provides the ability to see debug messages for deprecated functions, malformed documents and parsing issues. Debug messages can be sent to a custom message handler or written to error_log (default).

## Example

```php
<?php

require_once __DIR__. '/vendor/autoload.php';

use PHPCore\SimpleHtmlDom\Debug;use PHPCore\SimpleHtmlDom\HtmlDocument;

Debug::enable();

$dom = new HtmlDocument();
$dom->load('<html></html>');
$dom->root->children(); // This causes a deprecation warning

Debug::disable();
```

**Output**

```
[DEBUG] [/var/www/html/simplehtmldom/Debug.php:30] [/var/www/html/simplehtmldom/test.php:7] "Debug mode has been enabled"
[DEBUG] [/var/www/html/simplehtmldom/HtmlNode.php:83] [/var/www/html/simplehtmldom/test.php:11] "PHPCore\SimpleHtmlDom\HtmlNode->children() has been deprecated and will be removed in the next major version of simplehtmldom. Use PHPCore\SimpleHtmlDom\HtmlNode->childNodes() instead."
[DEBUG] [/var/www/html/simplehtmldom/Debug.php:38] [/var/www/html/simplehtmldom/test.php:13] "Debug mode has been disabled"
```
