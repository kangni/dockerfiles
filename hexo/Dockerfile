FROM node:8-alpine

WORKDIR /hexo

RUN \
    sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories && \
    apk --no-cache --update add git && \
    npm install -g hexo-cli && \
    npm install hexo-deployer-git --save

CMD ['/bin/ash']