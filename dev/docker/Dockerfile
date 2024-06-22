FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update && apt upgrade

RUN apt install -y nodejs

RUN apt install -y npm

RUN apt install -y default-jre

RUN apt install -y default-jdk

RUN apt install -y openssh-server

RUN mkdir -p /run/sshd && chmod 755 /run/sshd

RUN apt-get update && apt-get upgrade

RUN apt-get install -y curl

RUN apt-get install -y git

RUN apt-get install -y groovy

RUN apt-get install -y python3

RUN apt-get install -y python3-pip

RUN ln -s /usr/bin/python3 /usr/bin/python

RUN echo "[global]\nbreak-system-packages = true" > /etc/pip.conf

RUN npm install -g nodemon

RUN python -m pip install requests

RUN python -m pip install PyYAML

RUN python -m pip install Jinja2

CMD ["/usr/sbin/sshd", "-D"]