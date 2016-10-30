---
layout: post
title: Install DNSCrypt on Debian Jessie
summary:
status: draft
hn-discussion:
---

### DNSCrypt

[DNSCrypt](https://dnscrypt.org) is a protocol that authenticates communications between a DNS client and a DNS resolver. It prevents DNS spoofing. It uses cryptographic signatures to verify that responses originate from the chosen DNS resolver and haven't been tampered with.

Implementations are available for most operating systems, including Linux, OSX, Android, iOS, BSD and Windows.

[DNSCrypt](https://dnscrypt.org) is not affiliated with any company or organization, is a documented protocol using highly secure, non-NIST cryptography, and its reference implementations are open source and released under a very liberal license.

Please note that [DNSCrypt](https://dnscrypt.org) is not a replacement for a VPN, as it only authenticates DNS traffic, and doesn't prevent "DNS leaks", or third-party DNS resolvers from logging your activity.

### DNSCrypt-compatible public resolvers

A couple companies, organizations and individuals are operating public recursive DNS servers supporting the DNSCrypt protocol, so that all you need to run is the client.

A constantly updated [list of open DNSCrypt resolvers](https://github.com/jedisct1/dnscrypt-proxy/blob/master/dnscrypt-resolvers.csv) can be downloaded to replace the default CSV file shipped with the dnscrypt-proxy client.

If you are running your own public DNS resolver in order to help make the Internet a more secure place, please submit a [pull request](https://github.com/jedisct1/dnscrypt-proxy/pulls) to have your resolver added to the [list of open DNSCrypt resolvers](https://github.com/jedisct1/dnscrypt-proxy/blob/master/dnscrypt-resolvers.csv).

### Deployment

[DNSCrypt](https://dnscrypt.org) is typically deployed using a pair of DNS proxies: a client proxy and a server proxy.

The client side of DNSCrypt is a proxy to which regular DNS clients can connect to. Instead of using your ISP's DNS settings, you can just configure your network settings to use _127.0.0.1_ or whatever IP address and port you configured the DNSCrypt client to listen to. The client proxy translates regular DNS queries into authenticated DNS queries, forwards them to a server running the server DNSCrypt proxy, verifies the responses, and forwards them to the client if they appear to be genuine.

The server side of DNSCrypt receives DNS queries sent by the client proxy, forwards them to a trusted DNS resolver, and signs the responses it receives before forwarding them to the client proxy.

The DNSCrypt protocol uses UDP and TCP ports 443, which are less likely to be filtered by routers and ISPs than the standard DNS port.

The local network is usually the most vulnerable network segment against active attacks such as DNS spoofing. The DNSCrypt server can run on the router, along with a modern DNS resolver. Clients can then run the client code of DNSCrypt, leveraging the router DNS resolver.

### Instalation

Building [DNSCrypt](https://dnscrypt.org) from source can be compiled. The only dependency for it to compile is **libsodium** and **libsystemd** for which most distributions provide pre-built packages. The proxy will be installed as _/usr/local/sbin/dnscrypt-proxy_ by default

Command-line switches are documented in the dnscrypt-proxy(8) man page. Having a dedicated system user, with no privileges and with an empty home directory, is highly recommended. For extra security, DNSCrypt will chroot() to this user's home directory and drop root privileges for this user's uid as soon as possible.

### HOW TO?

Most users just want to start the client proxy like this:

> sudo dnscrypt-proxy --ephemeral-keys --resolver-name=<resolver name>

or

> sudo dnscrypt-proxy --ephemeral-keys --resolver-name=<resolver name> --daemonize
