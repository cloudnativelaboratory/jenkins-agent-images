FROM openjdk:8-jdk-alpine
LABEL maintainer="CloudNativeLab.COM <uname.chen@gmail.com>"

USER root

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories && \
    apk update && \
    apk add  --no-cache openrc docker git curl tar gcc g++ make \
    bash shadow openjdk8 python2 python2-dev py-pip openssl-dev libffi-dev \
    libstdc++ harfbuzz nss freetype ttf-freefont && \
    mkdir -p /root/.kube && \
    usermod -a -G docker root

COPY config /root/.kube/

RUN rm -rf /var/cache/apk/*

# with kubectl install
COPY kubectlv1.20.1 /usr/local/bin/kubectl
RUN chmod +x /usr/local/bin/kubectl
