
# Outrigger Varnish

> Varnish 4 container with a confd template that outputs a nice Drupal-compatible VCL

[![](https://images.microbadger.com/badges/version/outrigger/varnish.svg)](https://microbadger.com/images/outrigger/varnish "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/image/outrigger/varnish.svg)](https://microbadger.com/images/outrigger/varnish "Get your own image badge on microbadger.com")

This CentOS-based Varnish image has deep Drupal support and a number of
configurable options.

For more documentation on how Outrigger images are constructed and how to work
with them, please [see the documentation](http://docs.outrigger.sh/en/latest/).

## Features

### PURGE & PURGEALL

Support for HTTP request-based PURGING of cached data.

* PURGE is used to clear the specific URL.
* PURGEALL will wipe all content for the requested host.

PURGE requests may come from the Varnish local host, or the docker0 bridge network.

### Cache Tag Invalidation

Uses Varnish bans to clear cache based on Drupal 8 Cache tags via
[Purge](https://www.drupal.org/project/purge) module.

Applies the same access control as Purge uses.

## Environment Variables

Outrigger images use Environment Variables and [confd](https://github.com/kelseyhightower/confd)
to "templatize" a number of Docker environment configurations. These templates are
processed on startup with environment variables passed in via the docker run
command-line or via your docker-compose manifest file. Here are the "tunable"
configurations offered by this image.

* `VARNISH_BACKEND_HOST`: [`www`] Hostname Varnish uses for its backend.
* `VARNISH_BACKEND_PORT`: [`80`] Port number for the Varnish backend.
* `VARNISH_LISTEN_ADDRESS`: [`0.0.0.0`] IP address on which Varnish listens for
  requests to proxy.
* `VARNISH_LISTEN_PORT`: [`80`]: Port on which Varnish listens for requests to
  proxy.
* `VARNISH_ADMIN_LISTEN_ADDRESS`: [`0.0.0.0`] Wide open access to Varnish control.
* `VARNISH_ADMIN_LISTEN_PORT`: [`6082`] Port at which to access Varnish admin.
* `VARNISH_STORAGE`: [`"malloc,64M"`] Further storage configuration.
* `VARNISH_EXTRA_OPTS`: [`""`] Miscellaneous catch-all options passed to Varnish
  at container start. Empty by default.

## Security Reports

Please email outrigger@phase2technology with security concerns.

## Maintainers

[![Phase2 Logo](https://www.phase2technology.com/wp-content/uploads/2015/06/logo-retina.png)](https://www.phase2technology.com)
