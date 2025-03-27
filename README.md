<!-- vim: set ft=markdown : -->


# Biomappings curation app

## Prerequisites

### Required

* [Pixi](https://pixi.sh)

* Application capable of building and running Docker Compose stacks, such as
  [OrbStack](https://orbstack.dev)

### Optional

* Configure Git hooks:

    ``` shell
    pixi run -- pre-commit-install
    ```

## Decrypt secrets

``` shell
pixi run -- decrypt
```

## Update `/etc/hosts`

``` shell
printf -- '%s\n' \
    '::1 app.gyori-mac.localdomain' \
    '127.0.0.1 app.gyori-mac.localdomain' \
  | sudo -- tee -a -- /etc/hosts > /dev/null
```

## TLS cert

Place a trusted TLS cert with SAN `*.gyori-mac.localdomain` and corresponding key at
`~/.pki/private/x509/gyori-mac/{cert.pem,key.pem}`, respectively.

## Launch

``` shell
docker-compose up
```

[Biomappings curation app](https://app.gyori-mac.localdomain)
