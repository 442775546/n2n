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