# SmileEzCDNBundle

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/deca2593-f005-4866-9aec-a2ba30d681b1/mini.png)](https://insight.sensiolabs.com/projects/deca2593-f005-4866-9aec-a2ba30d681b1)

This bundle aims to replace or add CDN domain to specific resource provided by web page


## Installation

### Get the bundle using composer

Add SmileEzCDNBundle by running this command from the terminal at the root of
your eZPlatform project:

```bash
composer require smile/ez-cdn-bundle
```


### Enable the bundle

To start using the bundle, register the bundle in your application's kernel class:

```php
// ezpublish/EzPublishKernel.php
public function registerBundles()
{
    $bundles = array(
        // ...
        new Smile\EzCDNBundle\SmileEzCDNBundle(),
        // ...
    );
}
```

Care about Apache configuration when fonts (eot, woff ...) served by css, or ajax/cookie manipulation with javascript.
Refer to : http://www.w3.org/TR/cors/


### Configure bundle

```yaml
# ezpublish/config/config.yml
smile_ez_cdn:
    system:
        acme_group: #for each siteaccess
            domain: domain.tld #required, delare your CDN domain
            extensions: [png, css] # list of resource extension that would be serve by your CDN
```

