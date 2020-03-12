FROM amazonlinux:2018.03

# install packages
RUN yum -y update && yum clean all && \
    yum -y install \
    wget \
    git \
    awscli \
    openssh \
    openssh-server \
    tar \
    gcc \
    make \
    zlib-devel \
    openssl-devel \
    which \
    zip \
    unzip \
    glibc-langpack-ja \
    vim \
    sudo \
    mysql-devel

# set timezone
RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN echo "root:root" | chpasswd

# set SSHD
RUN sed -ri 's/^#PermitRootLogin yes/PermitRootLogin yes/' /etc/ssh/sshd_config && sed -ri 's/^UsePAM yes/UsePAM no/' /etc/ssh/sshd_config

# make user
RUN useradd ec2-user

# current directory
WORKDIR /home/ec2-user

# target ports
EXPOSE 22 80 443
