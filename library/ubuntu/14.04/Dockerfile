FROM ubuntu:14.04
MAINTAINER from "ssh_server_ubuntu"
RUN echo "deb http://mirrors.163.com/ubuntu/ trusty main restricted universe multiverse" > /etc/apt/sources.list
RUN echo "deb http://mirrors.163.com/ubuntu/ trusty-security main restricted universe multiverse" >> /etc/apt/sources.list
RUN echo "deb http://mirrors.163.com/ubuntu/ trusty-updates main restricted universe multiverse" >> /etc/apt/sources.list
RUN echo "deb http://mirrors.163.com/ubuntu/ trusty-proposed main restricted universe multiverse" >> /etc/apt/sources.list
RUN echo "deb http://mirrors.163.com/ubuntu/ trusty-backports main restricted universe multiverse" >> /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y openssh-server
RUN mkdir -p /var/run/sshd
RUN mkdir -p /root/.ssh
RUN sed -ri 's/#session    required     pam_loginuid.so/session    required     pam_loginuid.so/g' /etc/pam.d/sshd
RUN sed -ri 's/PermitRootLogin without-password /PermitRootLogin yes/g'  /etc/ssh/sshd_config
#ADD authorized_keys /root/.ssh/authorized_keys
RUN ls -l /root/.ssh/authorized_keys
EXPOSE 22
CMD ["/usr/sbin/sshd","-D"]

