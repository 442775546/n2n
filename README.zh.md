n2n
n2n 是一款轻量级的 VPN 软件，可以轻松创建绕过中间防火墙的虚拟网络。

为了开始使用 n2n，需要两个元素：

超级节点：它允许边缘节点宣布和发现其他节点。它必须具有可在 Internet 上公开访问的端口。
边缘节点：将成为虚拟网络一部分的节点
在 n2n 中的多个边缘节点之间共享的虚拟网络称为社区。单个超级节点可以中继多个社区，而一台计算机可以同时成为多个社区的一部分。边缘节点可以使用加密密钥来加密其社区内的数据包。

N2N 会尽可能尝试通过 UDP 在边缘节点之间建立直接的点对点连接。当这是不可能的（通常是由于特殊的 NAT 设备），超级节点也用于中继数据包。

快速设置
一些 Linux 发行版已经提供了 n2n 作为包，因此 simple 就可以完成这项工作。或者，大多数发行版的最新软件包都可以在 ntop 存储库中找到。sudo apt install n2n

在 host1 上运行：

$ sudo edge -c mynetwork -k mysecretpass -a 192.168.100.1 -f -l supernode.ntop.org:7777
在 host2 上运行：

$ sudo edge -c mynetwork -k mysecretpass -a 192.168.100.2 -f -l supernode.ntop.org:7777
现在，两台主机可以相互 ping作。

重要强烈建议选择自定义社区名称 （） 和秘密加密密钥 （），以防止其他用户连接到您的计算机。为了保护您发送的数据隐私，减少 的服务器负载，还建议设置一个自定义超级节点，如下所述。-c-ksupernode.ntop.org

设置自定义超级节点
您可以通过在公共服务器（例如 VPS）上设置超级节点来创建自己的基础设施。您只需在防火墙上打开一个端口（以下示例中为 1234）（通常为 ）。iptables

安装 n2n 软件包
编辑并添加以下内容：/etc/n2n/supernode.conf
-p=1234
使用 启动 supernode 服务sudo systemctl start supernode
（可选）启用 supernode start on boot：sudo systemctl enable supernode
现在，超级节点服务应该在端口 1234 上启动并运行。在您的边缘节点上，您现在可以指定使用它。所有边缘节点必须使用相同的超级节点。-l your_supernode_ip:1234

手动编译
在 Linux 上，从源代码编译非常简单：

./autogen.sh
./configure
make

# optionally install
make install
对于 Windows、MacOS、优化和通用构建选项，请查看构建文档以进行编译和运行。

重要通常建议使用最新的稳定版本。请注意，当前的 dev 分支通常不能保证与最新的稳定版本或以前的 dev 状态向后兼容。另一方面，如果您敢于尝试最前沿的功能，我们鼓励您从 dev 开始编译 – 只需跟踪有时快速发生的更改即可。感谢 Issues 部分的反馈。

安全注意事项
启用有效负载加密后（使用 提供密钥），超级节点将无法解密 两个边缘节点之间交换的流量，但它会知道边缘 A 正在与边缘 B 通信。-k

最近增强了可应用于 payload 的加密方案的选择。请拥有 查看 Crypto description 以获取快速比较图表，以帮助做出选择。N2N 边缘节点使用 默认为 AES 加密。可以使用该选项选择其他密码。-A_

使用 从源代码编译时，可以使用加密方法的基准测试。tools/n2n-benchmark

包含一些元数据的标头，例如边缘节点的虚拟 MAC 地址、其 IP 地址、实际 MAC 地址 hostname 和社区名称（可选）可以在 Edge 上应用加密。-H

<-------- by 刘琳锋------->
高级配置
有关社区、对多个超级节点的支持、路由、流量限制以及如何将边缘作为运行的更多信息 更详细的文档中提供了 Service。

贡献
您可以通过多种方式为 n2n 做出贡献：

更新未解决的问题或创建一个新问题并提供详细信息
提出新功能
改进文档
提供具有增强功能的拉取请求
有关 n2n 内部结构的详细信息，请查看 Hacking 指南。

延伸阅读和相关项目
常见问题的答案可以在我们的常见问题解答文档中找到。

以下是连接到此存储库的第三方项目列表：

适用于 Windows 的预构建二进制文件集合：lucktu
适用于 Android 的 n2n：hin2n
Docker 镜像：Docker Hub
用于n2n边缘和超级节点、Docker、Kubernetes和Helm图表的Go绑定、管理守护进程和CLI：pojntfx/gon2n
Windows GUI（以及 n2n 的自定义版本）也适用于常规 n2n：HappyNet
<-------- by 刘琳锋------->