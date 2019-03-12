# twig-php-helpers

This project is work-in-progress!

## local testing

extend your `$BoltDir/extensions/composer.json` with:
```json
"repositories": {
        "myrepo": {
            "type": "git",
            "url": "/Users/martin/projects/twig-php-helpers/"
        },
        "bolt": {
            "type": "composer",
            "url": "https://market.bolt.cm/satis/"
        },
        "packagist": false
    },
    "require": {
        "znegva/twig-php-helpers": "dev-master"
    },
```

AND make sure you have uncommented in your `config.yml`:
```yml
extensions:
    site: 'https://market.bolt.cm/'
    enabled: true
    composer:
        minimum-stability: dev      # Either 'stable', 'beta', or 'dev'. Setting 'dev' will allow you to install dev-master versions of extensions.
        prefer-stable: true            # Prefer stable releases over development ones
        prefer-dist: true              # Forces installation from package dist even for dev versions.
        prefer-source: false           # Forces installation from package sources when possible, including VCS information.
        config:
            optimize-autoloader: false     # Optimize autoloader during autoloader dump.
            classmap-authoritative: false  # Autoload classes from the classmap only. Implicitly enables `optimize-autoloader`.
```

Note the `minimum-stability: dev`, if you dont uncomment in `config.yml` `minimum-stability` in `$BoltDir/extensions/composer.json` will always be set to `stable` :arg:.