FROM node:12.18.3-alpine3.10
MAINTAINER littledian <1197434548@qq.com>

# set mirror
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories

# install git bash and set timezone ShangHai
RUN apk update \
  && apk upgrade \
  && apk add --no-cache bash \
  git \
  tzdata \
  docker-cli \
  && cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

# set registry
RUN npm config set registry https://registry.npm.taobao.org \
  && npm config set sass_binary_site https://npm.taobao.org/mirrors/node-sass \
  && yarn config set registry https://registry.npm.taobao.org \
  # smoke test
  && node --version \
  && npm --version \
  && yarn --version

CMD ["bash"]
