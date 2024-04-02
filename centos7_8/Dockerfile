# 使用官方的 CentOS 7 镜像作为基础镜像
FROM centos:7.8.2003

# 设置工作目录
WORKDIR /build

# 安装必要的依赖项和工具
RUN yum install -y epel-release && \
    yum install -y python3 python3-devel patchelf gcc gcc-c++ make && \
    python3 -m pip install --upgrade pip && \
    python3 -m pip install nuitka
