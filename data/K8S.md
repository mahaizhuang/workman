# Kubernetes运维
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

![虚拟化历史回溯](image/虚拟化历史回溯.png)
