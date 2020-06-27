# Stubby Docker Image - tailored for unRAID use

## What does this do?

This allows you to run a Stubby container for DNS over TLS support.

According to the [Stubby documentation](https://dnsprivacy.org/wiki/display/DP/About+Stubby):
> Unbound can be configured as a local forwarder using DNS-over-TLS to forward queries. However at the moment Unbound does not have all the TCP/TLC features that Stubby has for example, it cannot support 'Strict' mode, it cannot pad queries to hide query size and it opens a separate connection for every DNS query (Stubby will re-use connections)
>
>However, Unbound is a more mature and stable daemon and may be more reliable today. 

Stubby performs DNS resolution over TLS. By default, this is configured to use Cloudflare DNS. 

## How to use

### Standard usage

Next, point your DNS to the IP of your Docker host running the Unbound container.

## Acknowledgments

Many thanks to the original creator.  See original acknowledgements.
- Matthew Vance (https://github.com/MatthewVance/stubby-docker)


## Licenses
### License

Unless otherwise specified, all code is released under the MIT License (MIT). See the [repository's `LICENSE` file](https://github.com/fdm1980/stubby-docker/blob/fdm1980-unRAID/LICENSE) for details.
(originally from https://github.com/MatthewVance/stubby-docker)

### Licenses for other components

- DNSCrypt server Docker image: [ISC License](https://github.com/jedisct1/dnscrypt-server-docker/blob/master/LICENSE)
- Docker: [Apache 2.0](https://github.com/docker/docker/blob/master/LICENSE)
- OpenSSL: [Apache-style license](https://www.openssl.org/source/license.html)
- Stubby: [BSD-3-Clause](https://github.com/getdnsapi/getdns/blob/develop/LICENSE)
