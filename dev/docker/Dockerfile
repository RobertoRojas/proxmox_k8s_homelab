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

RUN echo '[global]\nbreak-system-packages = true' > /etc/pip.conf

RUN apt install apt-transport-https curl gnupg -y

RUN curl -fsSL https://bazel.build/bazel-release.pub.gpg | gpg --dearmor >bazel-archive-keyring.gpg

RUN mv bazel-archive-keyring.gpg /usr/share/keyrings

RUN echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/bazel-archive-keyring.gpg] https://storage.googleapis.com/bazel-apt stable jdk1.8' | sudo tee /etc/apt/sources.list.d/bazel.list

RUN apt install bazel

RUN curl -o /usr/bin/buildifier https://github.com/bazelbuild/buildtools/releases/download/v7.1.2/buildifier-linux-amd64

RUN chmod +x /usr/bin/buildifier

RUN curl -fsSL https://code-server.dev/install.sh | sh

RUN RUN code-server --install-extension bazelbuild.vscode-bazel

RUN RUN code-server --install-extension vscjava.vscode-gradle

RUN RUN code-server --install-extension vscjava.vscode-java-pack

RUN npm install -g nodemon

RUN python -m pip install requests

RUN python -m pip install PyYAML

RUN python -m pip install Jinja2

CMD ["/usr/sbin/sshd", "-D"]