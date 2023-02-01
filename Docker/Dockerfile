FROM  python:alpine3.16
LABEL maintainer="Vitaly Zverev"

# Set language to avoid bugs that sometimes appear
ENV LANG en_US.UTF-8

# Set up requirements
RUN echo "root:root" | chpasswd \
    && echo "http://dl-cdn.alpinelinux.org/alpine/edge/main" >> /etc/apk/repositories \
    && echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories \
    && apk add --no-cache \
      openconnect \
      openvpn \
      openssh \
      git \
      nmap \
    && mkdir ${HOME}/vpn && cd ${HOME}/vpn  && git clone https://gitlab.com/cpvpn/cpyvpn.git .  && git checkout 1.5.3 && python3 -m pip install . \
    && git clone https://gitlab.com/openconnect/vpnc-scripts.git \
    && mkdir  ${HOME}/.ssh

CMD ["sh", "-c", "echo \"${SSH_KEY}\" > ~/.ssh/authorized_keys && ssh-keygen -A && /usr/sbin/sshd && sh"]
