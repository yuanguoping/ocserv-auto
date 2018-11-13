Auto Install Ocserv Server for CentOS&RedHat 7
=======================================
这是 ocserv 在 CentOS 7 和 RHEL 7 的一键安装脚本，使用 epel 的二进制源，可以在最小化安装环境的 CentOS 7 和 RHEL 7 下一键部署 ocserv。

支持自动判断 firewalld 和 iptables，安装前请确保其中之一在运行。

* 支持自动判断防火墙，请确保 Firewalld 或者 iptables 其中一个是 active 状态；
* 默认采用用户名密码验证；
* 默认配置文件在 /etc/ocserv/ 目录；
* 安装时会提示你输入端口、用户名、密码等信息，也可直接回车采用默认值，密码是随机生成的；
* 安装脚本会关闭 SELINUX；
* 自带路由表，只有路由表里的 IP 才会走 VPN，如果你有需要添加的路由表可自行添加，最多支持 200 条；
* 如果你有证书机构颁发的证书，可以把证书放到脚本的同目录下，确保文件名和脚本里的匹配，安装脚本会使用你的证书，客户端连接时不会提示证书错误。
* 安装：
cd ocserv-auto
sh ocserv-auto
* 新增用户
ocpasswd -c /etc/ocserv/ocpasswd yeyiqu
* 启动
systemctl restart ocserv.service
