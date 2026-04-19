# Marble CMS Plugin Registry

This repository is the source of truth for the [Marble CMS](https://github.com/marblecms/marble) plugin marketplace.

The `registry.json` file in this repo is fetched directly by the Marble admin panel to enrich plugin listings with verified badges, featured status, screenshots, and tags.

## Browse plugins

Plugins are discovered via Packagist by searching for packages with `"type": "marble-plugin"`. The registry adds metadata on top.

## Publish a plugin

1. Build your plugin as a Composer package with `"type": "marble-plugin"`
2. Publish it on [Packagist](https://packagist.org)
3. Open a PR to add it to `registry.json`

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full schema and requirements.

## composer.json quickstart

```json
{
    "name": "vendor/marble-myplugin",
    "type": "marble-plugin",
    "require": {
        "marble/admin": "^1.0"
    },
    "extra": {
        "marble-plugin": {
            "name": "My Plugin",
            "description": "Does something great."
        }
    }
}
```
