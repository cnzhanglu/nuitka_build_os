# 使用官方的 CentOS 7 镜像作为基础镜像
FROM centos:7.8.2003

# 设置工作目录
WORKDIR /build

# 安装必要的依赖项和工具
RUN yum install -y epel-release && \
    yum install -y python3 python3-devel patchelf gcc gcc-c++ make git wget openssh-server passwd && \
    yum clean all && \
    rm -rf /var/cache/yum && \
    python3 -m pip install --upgrade pip && \
    python3 -m pip install nuitka
    
# 配置 OpenSSH 服务
RUN ssh-keygen -A && \
    echo 'root:password' | chpasswd && \
    sed -i 's/#PermitRootLogin yes/PermitRootLogin yes/' /etc/ssh/sshd_config

# 开放 SSH 服务端口
EXPOSE 22

# 定义容器启动命令
CMD ["/usr/sbin/sshd", "-D"]
