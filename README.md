# Stubby Docker Image - tailored for unRAID use

## What does this do?

This allows you to run a Stubby container for DNS over TLS support.

According to the [Stubby documentation](https://dnsprivacy.org/wiki/display/DP/About+Stubby):
> Unbound can be configured as a local forwarder using DNS-over-TLS to forward queries. However at the moment Unbound does not have all the TCP/TLC features that Stubby has for example, it cannot support 'Strict' mode, it cannot pad queries to hide query size and it opens a separate connection for every DNS query (Stubby will re-use connections)
>
>However, Unbound is a more mature and stable daemon and may be more reliable today. 

Stubby performs DNS resolution over TLS. By default, this container is configured to use Cloudflare DNS. 

## How to use - unRAID template setup
(assuming you use other DNS containers with "Network Type = Custom : br0" such as pihole or unbound)

1.  Network Type = Custom : br0  
  a.  Set your own IP address
  
2.  Port Mapping  
  a.  Name:  Host Port 1  
  b.  Host Port:  53  
  c.  Connection Type:  TCP

3.  Port Mapping  
  a.  Name:  Host Port 2  
  b.  Host Port:  53  
  c.  Connection Type:  UDP  

4.  Path/Volume Mapping  
  a.  Name:  Appdata  
  b.  Container Path:  /opt/stubby/etc/stubby/  
  c.  Host Path:  /mnt/user/appdata/stubby/  
  d.  Access Mode:  Read/Write  
  
Start the container to allow it to create the "/appdata/stubby/" folder.  
Stop the containter.  
Download/copy the [stubby.yml](https://github.com/fdm1980/stubby/blob/master/stubby/stubby.yml) file to the appdata folder.
Restart the container.

### Standard usage

Point your DNS to the IP of the Stubby container.

Open the console and type "stubby -V" to see the version.  
https://github.com/getdnsapi/stubby/releases

## Acknowledgments

Many thanks to the original creator.  See original acknowledgements.
- Matthew Vance (https://github.com/MatthewVance/stubby-docker)


## Licenses
### License

Unless otherwise specified, all code is released under the MIT License (MIT). See the [repository's `LICENSE` file](https://github.com/fdm1980/stubby/blob/master/LICENSE) for details.  
(originally from https://github.com/MatthewVance/stubby-docker)

### Licenses for other components

- DNSCrypt server Docker image: [ISC License](https://github.com/jedisct1/dnscrypt-server-docker/blob/master/LICENSE)
- Docker: [Apache 2.0](https://github.com/docker/docker/blob/master/LICENSE)
- OpenSSL: [Apache-style license](https://www.openssl.org/source/license.html)
- Stubby: [BSD-3-Clause](https://github.com/getdnsapi/getdns/blob/develop/LICENSE)
