Carbon.Notification Package for Neos CMS
========================================

[![Latest Stable Version](https://poser.pugx.org/carbon/notification/v/stable)](https://packagist.org/packages/carbon/notification)
[![Total Downloads](https://poser.pugx.org/carbon/notification/downloads)](https://packagist.org/packages/carbon/notification)
[![License](https://poser.pugx.org/carbon/notification/license)](https://packagist.org/packages/carbon/notification)

This package provides a tiny fusion helper for notifications.

[Carbon.Notification:Tag](Resources/Private/Fusion/Tag.fusion)
--------------------------------------------------------------
Add a notification. `type` can be `alert`, `warning` (default) or `info`.
You need to set `content` to get the notification show.
Great for NodeTypes who need an input in the inspector.

[Carbon.Notification:Backend](Resources/Private/Fusion/Backend.fusion)
----------------------------------------------------------------------
A variant from `Carbon.Notification:Tag`. This notification get only shown in the backend.


Installation
------------

Most of the time you have to make small adjustments to a package (e.g. configuration in `Settings.yaml`). Because of that, it is important to add the corresponding package to the composer from your theme package. Mostly this is the site packages located under `Packages/Sites/`. To install it correctly go to your theme package (e.g.`Packages/Sites/Foo.Bar`) and run following command:
```
composer require carbon/notification --no-update
```

The `--no-update` command prevent the automatic update of the dependencies. After the package was added to your theme `composer.json`, go back to the root of the Neos installation and run `composer update`. Et voilà! Your desired package is now installed correctly.


License
-------

Licensed under MIT, see [LICENSE](LICENSE)
