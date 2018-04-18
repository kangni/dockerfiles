FROM python:3.6-alpine3.7 AS release
WORKDIR /workspace
RUN apk add --no-cache --update gcc g++ freetype-dev libpng-dev && \
    ln -s /usr/include/locale.h /usr/include/xlocale.h && \
    pip3 install --no-cache-dir bcolz cython rqalpha jupyter -i https://pypi.doubanio.com/simple
CMD ["/bin/ash"]