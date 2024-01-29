FROM ubuntu:22.04
RUN DEBIAN_FRONTEND=noninteractive \
  apt-get update \
  && apt-get install -y net-tools tcpdump ifstat iperf htop openssh-server \
                        locales sudo iproute2 vim less kmod vlan iputils-ping \
  && rm -rf /var/lib/apt/lists/*
RUN mkdir /var/run/sshd
RUN useradd -ms /bin/bash aantonov
RUN usermod -aG sudo aantonov
RUN echo 'aantonov ALL=(ALL:ALL) NOPASSWD:ALL' >> /etc/sudoers
RUN echo 'en_US.UTF-8 UTF-8' >> /etc/locale.gen
RUN locale-gen
RUN mkdir -p /home/aantonov/.ssh \
    chmod 0700 /home/aantonov/.ssh
COPY id_rsa.pub /home/aantonov/.ssh/authorized_keys
RUN chown -R aantonov:aantonov /home/aantonov
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
