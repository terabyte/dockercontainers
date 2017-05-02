FROM debian:latest
MAINTAINER Carl Myers

RUN echo 'deb http://ftp.us.debian.org/debian/ jessie main non-free contrib' >> /etc/apt/sources.list.d/01-cmyers.list
RUN echo 'deb-src http://ftp.us.debian.org/debian/ jessie main non-free contrib' >> /etc/apt/sources.list.d/01-cmyers.list
RUN echo 'deb http://ftp.debian.org/debian jessie-backports main' >> /etc/apt/sources.list.d/01-cmyers.list
RUN apt-get update
RUN apt-get install -t jessie-backports -y openjdk-8-jdk
RUN apt-get install -y vim sudo git curl wget less zsh tmux

RUN mkdir /root/.ssh
RUN chmod 755 /root/.ssh

ADD idrsa /root/.ssh/idrsa
RUN chmod 600 /root/.ssh/idrsa

ADD *.sh /root/
RUN chmod +x /root/*.sh

# TODO: how do I get these values dynamically?
RUN git config --global user.name "Carl Myers"
RUN git config --global user.email "cmyers@cmyers.org"

# CMD ["/bin/bash"]
