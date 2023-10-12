+++
title = "My Personal Servers"
date = 2023-10-10

[taxonomies]
tags = ["servers", "homelab"]
+++

I run several servers in both the cloud and in my home, as to reduce my
dependency on
[SaaSS](https://www.gnu.org/philosophy/who-does-that-server-really-serve.en.html)
products. It's certainly been an adventure, but I think overall it's been a good
one.

## Servers

| Server | Specs                                                   | Operating System | Services          |
| ------ | ------------------------------------------------------- | ---------------- | ----------------- |
| Osiris | 1 vCPU, 1GB RAM [Vultr](https://vultr.com) instance     | Debian 12        | Website, VPN      |
| Nile   | HP ProLiant ML350p, Xeon E5-2640v2, 64GB ECC DDR4       | XCP-ng           | Virtualization    |
| Atum   | 2 vCPU, 4GB RAM XCP-ng VM                               | Debian 12        | Xen Orchestra     |
| Anubis | Celeron N5105, 16GB RAM, Generic AliExpress Motherboard | Ubuntu 22.04     | NAS, Media Server |
