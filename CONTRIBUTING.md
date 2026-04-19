# Contributing to the Marble CMS Plugin Registry

This repository is the official registry for Marble CMS plugins. It powers the **Plugins** section in the Marble admin panel.

## How to list your plugin

1. Make sure your package is published on [Packagist](https://packagist.org) with `"type": "marble-plugin"` in your `composer.json`.
2. Fork this repository.
3. Add your package to `registry.json` (see schema below).
4. Open a Pull Request.

## registry.json schema

```json
{
    "vendor/package-name": {
        "verified": false,
        "featured": false,
        "tags": ["tag1", "tag2"],
        "screenshots": [
            "https://example.com/screenshot1.png"
        ],
        "readme_url": "https://github.com/vendor/package-name#readme"
    }
}
```

| Field          | Type       | Required | Description |
|----------------|------------|----------|-------------|
| `verified`     | boolean    | yes      | Set to `true` only by Marble CMS maintainers after review |
| `featured`     | boolean    | yes      | Set to `true` only by Marble CMS maintainers |
| `tags`         | string[]   | yes      | Relevant keywords (max 5) |
| `screenshots`  | string[]   | no       | Direct URLs to screenshots (max 5, min 800px wide) |
| `readme_url`   | string     | no       | Link to documentation or README |

## Verified badge

The `verified` badge is awarded by the Marble CMS team after we review the plugin for:
- Security (no eval, no arbitrary code execution, no data exfiltration)
- Code quality
- Compatibility with the current Marble version

## composer.json requirements

Your plugin's `composer.json` must include:

```json
{
    "name": "vendor/marble-yourplugin",
    "type": "marble-plugin",
    "require": {
        "marble/admin": "^1.0"
    },
    "extra": {
        "marble-plugin": {
            "name": "Your Plugin Name",
            "description": "Short description shown in the marketplace."
        }
    }
}
```
