<!-- by 文荣平 -->
### 快速设置
- **安装方式**：部分Linux发行版已将 `n2n` 作为软件包提供，可使用 `sudo apt install n2n` 进行安装。此外，大多数发行版的最新软件包可在 [ntop repositories](http://packages.ntop.org/) 中获取。
- **示例配置**：在不同主机上配置边缘节点的示例如下：
```sh
# 以sudo权限运行edge命令，配置n2n边缘节点
# -c 参数指定社区名称为 mynetwork
# -k 参数指定加密密钥为 mysecretpass
# -a 参数指定本地IP地址为 192.168.100.1
# -f 参数表示以前台模式运行
# -l 参数指定连接到的超级节点为 supernode.ntop.org:7777
```
    - 主机1：
```sh
sudo edge -c mynetwork -k mysecretpass -a 192.168.100.1 -f -l supernode.ntop.org:7777
```

    - 主机2：
```sh
sudo edge -c mynetwork -k mysecretpass -a 192.168.100.2 -f -l supernode.ntop.org:7777
```

配置完成后，两台主机可以相互ping通。强烈建议选择自定义社区名称（`-c`）和秘密加密密钥（`-k`），以防止其他用户连接到您的计算机。为保护数据隐私、减少 `supernode.ntop.org` 的服务器负载，还建议设置自定义超级节点。

