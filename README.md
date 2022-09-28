[![Latest stable version]][packagist] [![Total downloads]][packagist] [![License]][packagist] [![GitHub forks]][fork] [![GitHub stars]][stargazers] [![GitHub watchers]][subscription]

# Carbon.Notification Package for Neos CMS

This package provides a tiny fusion helper for notifications:

Type `info`
![screenshot info]

Type `warning`
![screenshot warning]

Type `alert`
![screenshot alert]

Type `success`
![screenshot success]

Besides these four types, there is also the type `backend`, which on a document,
which is in the colors of the Neos Backend, is ideal for a notification.
![screenshot backend]

## [Carbon.Notification:Tag]

Adds a notification. `type` can be `alert`, `warning` (default), `info`, `success` or
`backend`. You need to set `content` to get the notification showing. If you want to
add/change a style, you can pass a key/value pair to it. For example, you want to
alter the `padding` and want to change the `font-weight` to `bold` you can enter:

```elm
notification = Carbon.Notification:Tag {
    padding = '12px'
    font-weight = 'bold'

    content = 'Here comes your content'
}
```

With the `lang` attribute you can set an alternative language. Useful if your interface
and website languages differ from each other.

## [Carbon.Notification:Backend]

A variant from `Carbon.Notification:Tag`.
This notification gets only shown in the backend. Great for NodeTypes, who need
input in the inspector. It has the same capabilities as [Carbon.Notification:Tag],
it is just extended with `@if.inBackend = ${node.context.inBackend}`

## [Carbon.Notification:Data]

Add a notification to the backend view. You need to set `content` to get the
notification showing. This is great for NodeTypes, who need input in the inspector.
Add this prototype to `data-carbon-alert`, `data-carbon-warning`,
`data-carbon-info` or `data-carbon-backend` to an element as attribute.
You can also pass directly `data-carbon-*` to an element. If the HTML element has no content,
the message is shown, otherwise, it will be hidden. This is done with the CSS selector `:not(:emtpy)`

A use-case for this if you want to show a notification if a content collection is empty.

## [Carbon.Notification:Document]

This sourounds `Carbon.Notification:Tag` with the needed `HTML` Markup for a document.

## Customization

Every notification load the default styles from the settings `Carbon.Notification.default`. If you
want to change some values or add new ones, you can edit them in your `Settings.yaml`.

Per default, there are five types of notification configured. If you want to add your own types,
you can extend the setting `Carbon.Notification.types` with your own entries.

For further details, please take a look at the file [`Settings.Carbon.yaml`]

## Installation

Most of the time you have to make small adjustments to a package (e.g.
configuration in `Settings.yaml`). Because of that, it is important to add the
corresponding package to the composer from your theme package. Mostly this is
the site package located under `Packages/Sites/`. To install it correctly go to
your theme package (e.g.`Packages/Sites/Foo.Bar`) and run following command:

```bash
composer require carbon/notification --no-update
```

The `--no-update` command prevent the automatic update of the dependencies.
After the package was added to your theme `composer.json`, go back to the root
of the Neos installation and run `composer update`. Et voilà! Your desired
package is now installed correctly.

[packagist]: https://packagist.org/packages/carbon/notification
[latest stable version]: https://poser.pugx.org/carbon/notification/v/stable
[total downloads]: https://poser.pugx.org/carbon/notification/downloads
[license]: https://poser.pugx.org/carbon/notification/license
[github forks]: https://img.shields.io/github/forks/CarbonPackages/Carbon.Notification.svg?style=social&label=Fork
[github stars]: https://img.shields.io/github/stars/CarbonPackages/Carbon.Notification.svg?style=social&label=Stars
[github watchers]: https://img.shields.io/github/watchers/CarbonPackages/Carbon.Notification.svg?style=social&label=Watch
[fork]: https://github.com/CarbonPackages/Carbon.Notification/fork
[stargazers]: https://github.com/CarbonPackages/Carbon.Notification/stargazers
[subscription]: https://github.com/CarbonPackages/Carbon.Notification/subscription
[carbon.notification:tag]: Resources/Private/Fusion/Components/Tag.fusion
[carbon.notification:backend]: Resources/Private/Fusion/Components/Backend.fusion
[carbon.notification:document]: Resources/Private/Fusion/Components/Document.fusion
[carbon.notification:data]: Resources/Private/Fusion/Components/Data.fusion
[`settings.carbon.yaml`]: Configuration/Settings.Carbon.yaml
[screenshot alert]: https://user-images.githubusercontent.com/4510166/77485453-7bedff00-6e2d-11ea-9795-97aab52ded6d.png
[screenshot backend]: https://user-images.githubusercontent.com/4510166/77485456-7db7c280-6e2d-11ea-87f4-969713364f07.png
[screenshot info]: https://user-images.githubusercontent.com/4510166/77485458-7e505900-6e2d-11ea-88f9-2b579bb92d9e.png
[screenshot success]: https://user-images.githubusercontent.com/4510166/77485460-7ee8ef80-6e2d-11ea-8b1e-ce54cb3e9a7b.png
[screenshot warning]: https://user-images.githubusercontent.com/4510166/77485461-7ee8ef80-6e2d-11ea-98df-fab3a134b814.png
