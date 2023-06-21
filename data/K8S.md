# Kubernetes运维
![虚拟化历史回溯](/image/虚拟化历史回溯.png)

## K8S基本知识
### K8S在linux的文件分布

+ /etc/kubernetes：Kubernetes的配置文件目录，包含了Kubernetes各个组件的配置文件。
+ /var/lib/kubelet：kubelet的数据目录，包含了kubelet的缓存数据、Pod的状态等信息。
+ /var/lib/kube-proxy：kube-proxy的数据目录，包含了kube-proxy的缓存数据、服务的状态等信息。
+ /var/lib/kubernetes：Kubernetes的数据目录，包含了etcd存储的数据、Kubernetes的证书、秘钥等信息。
+ /var/log/kubernetes：Kubernetes的日志目录，包含了Kubernetes各个组件的日志信息。
+ /opt/cni/bin：CNI插件的二进制文件目录，包含了Kubernetes网络插件的二进制文件。
+ /opt/cni/net.d：CNI插件的配置文件目录，包含了Kubernetes网络插件的配置文件。
+ /usr/local/bin：Kubernetes二进制文件目录，包含了Kubernetes各个组件的二进制文件。

### 为什么需要 Kubernetes，它能做什么？

    + 服务发现和负载均衡

    Kubernetes 可以使用 DNS 名称或自己的 IP 地址来暴露容器。 如果进入容器的流量很大， Kubernetes 可以负载均衡并分配网络流量，从而使部署稳定。

    存储编排

    Kubernetes 允许你自动挂载你选择的存储系统，例如本地存储、公共云提供商等。

    自动部署和回滚

    你可以使用 Kubernetes 描述已部署容器的所需状态， 它可以以受控的速率将实际状态更改为期望状态。 例如，你可以自动化 Kubernetes 来为你的部署创建新容器， 删除现有容器并将它们的所有资源用于新容器。

    自动完成装箱计算

    你为 Kubernetes 提供许多节点组成的集群，在这个集群上运行容器化的任务。 你告诉 Kubernetes 每个容器需要多少 CPU 和内存 (RAM)。 Kubernetes 可以将这些容器按实际情况调度到你的节点上，以最佳方式利用你的资源。

    自我修复

    Kubernetes 将重新启动失败的容器、替换容器、杀死不响应用户定义的运行状况检查的容器， 并且在准备好服务之前不将其通告给客户端。

    密钥与配置管理

    Kubernetes 允许你存储和管理敏感信息，例如密码、OAuth 令牌和 SSH 密钥。 你可以在不重建容器镜像的情况下部署和更新密钥和应用程序配置，也无需在堆栈配置中暴露密钥。

