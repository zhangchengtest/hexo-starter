title: magento install
date: 2017-06-13 13:19:23
tags:
---
title: magento install
tags:
---

```
PHP Fatal error:  Uncaught Error: Call to undefined function toHtml() in /var/www/magento1X/app/code/core/Mage/Core/Model/Layout.php:555

because the problem of the php7

Go to app\code\core\Mage\Core\Model\Layout.php line no 555 and

change $callback[1] to {$callback[1]}
```

