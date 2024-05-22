# 使用Ubuntu作为基础镜像
FROM ubuntu:20.04

# 设置非交互模式，避免安装过程中的询问
ARG DEBIAN_FRONTEND=noninteractive

# 更新 APT 源列表为阿里云源
RUN sed -i 's@archive.ubuntu.com@mirrors.tuna.tsinghua.edu.cn/ubuntu/@g' /etc/apt/sources.list && \
    sed -i 's@security.ubuntu.com@mirrors.tuna.tsinghua.edu.cn/ubuntu/@g' /etc/apt/sources.list

# 更新软件包缓存并安装必要的软件
RUN apt-get update && apt-get install -y \
    bash-completion \
    curl \
    vim

RUN apt-get update && apt-get install -y \
    autoconf \
    automake \
    build-essential \
    cmake \
    git \
    pkg-config \
    texinfo \
    wget \
    yasm \
    zlib1g-dev

# 启用bash命令自动补全
RUN echo "if [ -f /etc/bash_completion ] && ! shopt -oq posix; then" \
    "    . /etc/bash_completion" \
    "fi" >> ~/.bashrc



# 设置工作目录
WORKDIR /data

# 设置默认命令
CMD ["/bin/bash"]

