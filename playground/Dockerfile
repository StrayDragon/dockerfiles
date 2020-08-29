FROM alpine:latest

ENV PATH /usr/local/bin:$PATH
# ENV LANG=en_US.UTF-8

# apk 国内镜像
# RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories

# 一大堆基础依赖
RUN set -xe \
  && apk add --no-cache tmux go python3 py3-pip bash bash-doc bash-completion \
  && rm -rf /var/cache/apk/* 

# Pip 国内镜像
RUN pip config set global.index-url http://mirrors.aliyun.com/pypi/simple \
  && pip config set install.trusted-host mirrors.aliyun.com 

# Go mod 国内镜像
RUN go env -w GO111MODULE=on \
  && go env -w GOPROXY=https://goproxy.cn,direct
