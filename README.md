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