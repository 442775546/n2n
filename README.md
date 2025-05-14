<!-- by 文荣平  -->
### Quick Setup
- **Installation Method**: In some Linux distributions, `n2n` is provided as a software package, and you can install it using `sudo apt install n2n`. Additionally, the latest software packages for most distributions can be obtained from [ntop repositories](http://packages.ntop.org/).
- **Example Configuration**: Here are examples of configuring edge nodes on different hosts:
```sh
# Run the edge command with sudo privileges to configure an n2n edge node
# -c specifies the community name as mynetwork
# -k specifies the encryption key as mysecretpass
# -a specifies the local IP address as 192.168.100.1
# -f runs the process in foreground mode
# -l specifies the supernode to connect to as supernode.ntop.org:7777
```
    - Host 1:
```sh
sudo edge -c mynetwork -k mysecretpass -a 192.168.100.1 -f -l supernode.ntop.org:7777
```
    - Host 2:
```sh
sudo edge -c mynetwork -k mysecretpass -a 192.168.100.2 -f -l supernode.ntop.org:7777
```

After the configuration is completed, the two hosts can ping each other. It is highly recommended to choose a custom community name (`-c`) and a secret encryption key (`-k`) to prevent other users from connecting to your computer. To protect data privacy and reduce the server load of `supernode.ntop.org`, it is also recommended to set a custom supernode. 


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
