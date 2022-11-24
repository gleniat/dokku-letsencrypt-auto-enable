# dokku-letsencrypt-auto-enable

This plugin for Dokku automatically enables Let's encrypt HTTPS for all apps by default. To prevent enabling LE for a specific app, you can add `DOKKU_LETSENCRYPT_AUTO_ENABLE` environment variable and set it to `0`.

## Installation

```shell
dokku plugin:install https://github.com/gleniat/dokku-letsencrypt-auto-enable.git letsencrypt-auto-enable
```

Make sure you have [dokku-letsencrypt](https://github.com/dokku/dokku-letsencrypt) plugin installed and working correctly (i.e., you have set `DOKKU_LETSENCRYPT_EMAIL` per app or globally).

## Usage

1. Install the plugin

2. Rebuild your app(s), or create a new one. Let's Encrypt certificate will be obtained automatically after first successful deployment of the app.

`dokku letsencrypt:disable <yourapp>` will work until a subsequent build. To prevent enabling LE for the app permanently, please add `DOKKU_LETSENCRYPT_AUTO_ENABLE` environment variable and set it to `0`.

## Other variants

1. Activate Let's Encrypt automatically only for allowed apps. You must add `DOKKU_LETSENCRYPT_AUTO_ENABLE` and set it to `1` to enable the plugin. Try https://github.com/gleniat/dokku-letsencrypt-auto-enable-allow-list for this behavior.

## Requirements

- dokku 0.4.x
