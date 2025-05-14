


<-------by 刘琳锋-------->
## Advanced Configuration

More information about communities, support for multiple supernodes, routing, traffic restrictions and on how to run an edge as 
a service is available in the [more detailed documentation](doc/Advanced.md).


## Contribution

You can contribute to n2n in various ways:

- Update an [open issue](https://github.com/ntop/n2n/issues) or create a new one with detailed information
- Propose new features
- Improve the documentation
- Provide pull requests with enhancements

For details about the internals of n2n check out the [Hacking guide](https://github.com/ntop/n2n/blob/dev/doc/Hacking.md).


## Further Readings and Related Projects

Answers to frequently asked questions can be found in our [FAQ document](https://github.com/ntop/n2n/blob/dev/doc/Faq.md).

Here is a list of third-party projects connected to this repository:

- Collection of pre-built binaries for Windows: [lucktu](https://github.com/lucktu/n2n)
- n2n for Android: [hin2n](https://github.com/switch-iot/hin2n)
- Docker images: [Docker Hub](https://hub.docker.com/r/supermock/supernode/)
- Go bindings, management daemons and CLIs for n2n edges and supernodes, Docker, Kubernetes & Helm Charts: [pojntfx/gon2n](https://pojntfx.github.io/gon2n/)
- Windows GUI (along with a custom version of n2n) but also working with regular n2n: [HappyNet](https://github.com/happynclient/happynwindows)

---

(C) 2007-22 - ntop.org and contributors

<-------by 刘琳锋-------->

## Introduction to N2N Lightweight VPN
N2N is a lightweight VPN software that can bypass the restrictions of intermediate firewalls and easily create virtual networks. It is applicable to various scenarios such as enterprise network establishment and remote work.
## Core Components
1.Supernode: Serving as the network hub, it is responsible for the registration and discovery of edge nodes. It requires a publicly accessible port on the public network and supports concurrent relay of multiple communities.
2.Edge Node: As the terminal node of the virtual network, it supports multi-platform deployment. A single device can simultaneously join multiple communities and has the AES-256 data encryption function.
## Virtual Community Mechanism
N2N divides virtual networks through "communities". Each community has an independent network space and encryption key, and supports custom identification. A single supernode can manage hundreds of communities and achieve dynamic connection of members.
## Intelligent Connection Strategy
1.-UDP Direct Connection: Based on NAT traversal technology, it features zero latency and high bandwidth.
2.-Supernode Relay: Achieves reliable UDP transmission and automatically optimizes the connection.
3.-Hybrid Mode: Dynamically switches connections to ensure transmission stability.
## Security Protection
It provides multi-level security protection such as community-level AES-256 encryption, identity authentication, and data packet verification, and also supports regular key rotation.

