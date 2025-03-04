`heroku certs`
==============

a topic for the ssl plugin

* [`heroku certs`](#heroku-certs)
* [`heroku certs:add CRT KEY`](#heroku-certsadd-crt-key)
* [`heroku certs:auto`](#heroku-certsauto)
* [`heroku certs:auto:disable`](#heroku-certsautodisable)
* [`heroku certs:auto:enable`](#heroku-certsautoenable)
* [`heroku certs:auto:refresh`](#heroku-certsautorefresh)
* [`heroku certs:chain`](#heroku-certschain)
* [`heroku certs:generate DOMAIN`](#heroku-certsgenerate-domain)
* [`heroku certs:info`](#heroku-certsinfo)
* [`heroku certs:key`](#heroku-certskey)
* [`heroku certs:remove`](#heroku-certsremove)
* [`heroku certs:update CRT KEY`](#heroku-certsupdate-crt-key)

## `heroku certs`

list SSL certificates for an app

```
list SSL certificates for an app


USAGE
  $ heroku certs

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/index.js)_

## `heroku certs:add CRT KEY`

add an SSL certificate to an app

```
add an SSL certificate to an app
Note: certificates with PEM encoding are also valid

USAGE
  $ heroku certs:add CRT KEY

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
  --bypass             bypass the trust chain completion step
  --type=type          type to create, either 'sni' or 'endpoint'

DESCRIPTION
  Note: certificates with PEM encoding are also valid

EXAMPLES
  $ heroku certs:add example.com.crt example.com.key

  Certificate Intermediary:
  $ heroku certs:add intermediary.crt example.com.crt example.com.key
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/add.js)_

## `heroku certs:auto`

show ACM status for an app

```
show ACM status for an app


USAGE
  $ heroku certs:auto

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
  --wait               watch ACM status and display the status when complete
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/auto/index.js)_

## `heroku certs:auto:disable`

disable ACM for an app

```
disable ACM for an app


USAGE
  $ heroku certs:auto:disable

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/auto/disable.js)_

## `heroku certs:auto:enable`

enable ACM status for an app

```
enable ACM status for an app


USAGE
  $ heroku certs:auto:enable

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
  --wait               watch ACM status and exit when complete
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/auto/enable.js)_

## `heroku certs:auto:refresh`

refresh ACM for an app

```
refresh ACM for an app


USAGE
  $ heroku certs:auto:refresh

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/auto/refresh.js)_

## `heroku certs:chain`

print an ordered & complete chain for a certificate

```
print an ordered & complete chain for a certificate


USAGE
  $ heroku certs:chain

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/chain.js)_

## `heroku certs:generate DOMAIN`

generate a key and a CSR or self-signed certificate

```
generate a key and a CSR or self-signed certificate
Generate a key and certificate signing request (or self-signed certificate)
for an app. Prompts for information to put in the certificate unless --now
is used, or at least one of the --subject, --owner, --country, --area, or
--city options is specified.

USAGE
  $ heroku certs:generate DOMAIN

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
  --area=area          sub-country area (state, province, etc.) of owner
  --city=city          city of owner
  --country=country    country of owner, as a two-letter ISO country code
  --keysize=keysize    RSA key size in bits (default: 2048)
  --now                do not prompt for any owner information
  --owner=owner        name of organization certificate belongs to
  --selfsigned         generate a self-signed certificate instead of a CSR
  --subject=subject    specify entire certificate subject

DESCRIPTION
  Generate a key and certificate signing request (or self-signed certificate)
  for an app. Prompts for information to put in the certificate unless --now
  is used, or at least one of the --subject, --owner, --country, --area, or
  --city options is specified.

EXAMPLES
  $ heroku certs:generate example.com
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/generate.js)_

## `heroku certs:info`

show certificate information for an SSL certificate

```
show certificate information for an SSL certificate


USAGE
  $ heroku certs:info

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
  --endpoint=endpoint  endpoint to check info on
  --name=name          name to check info on
  --show-domains       show associated domains
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/info.js)_

## `heroku certs:key`

print the correct key for the given certificate

```
print the correct key for the given certificate
You must pass one single certificate, and one or more keys.
The first key that signs the certificate will be printed back.

USAGE
  $ heroku certs:key

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use

DESCRIPTION
  You must pass one single certificate, and one or more keys.
  The first key that signs the certificate will be printed back.

EXAMPLES
  $ heroku certs:key example.com.crt example.com.key
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/key.js)_

## `heroku certs:remove`

remove an SSL certificate from an app

```
remove an SSL certificate from an app


USAGE
  $ heroku certs:remove

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
  --endpoint=endpoint  endpoint to remove
  --name=name          name to remove
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/remove.js)_

## `heroku certs:update CRT KEY`

update an SSL certificate on an app

```
update an SSL certificate on an app
Note: certificates with PEM encoding are also valid

USAGE
  $ heroku certs:update CRT KEY

OPTIONS
  -a, --app=app        (required) app to run command against
  -r, --remote=remote  git remote of app to use
  --bypass             bypass the trust chain completion step
  --endpoint=endpoint  endpoint to update
  --name=name          name to update

DESCRIPTION
  Note: certificates with PEM encoding are also valid

EXAMPLES
  $ heroku certs:update example.com.crt example.com.key

  Certificate Intermediary:
  $ heroku certs:update intermediary.crt example.com.crt example.com.key
```

_See code: [@heroku-cli/plugin-certs-v5](https://github.com/heroku/cli/blob/v7.57.0/packages/certs-v5/commands/certs/update.js)_
