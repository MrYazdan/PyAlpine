FROM python:3.10-alpine

LABEL version="1.0"
LABEL maintainer="MrYazdan.ir <<mrrezayazdani@yahoo.com>>"

WORKDIR /usr/src/app

ENV LANG en_US.utf8
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

COPY . /usr/src/app/

RUN apk add --no-cache --virtual .build-deps \
		coreutils \
        ca-certificates openssl-dev \
		dpkg-dev dpkg \
		gcc clang g++ libc-dev \
		libedit-dev \
		libxml2-dev \
		libxslt-dev \
		linux-headers \
		llvm-dev \
		make \
        musl-dev \
        libffi-dev jpeg-dev zlib-dev \
        postgresql-dev \
		util-linux-dev \
		zlib-dev icu-dev lz4-dev ${PyAlpine_PACKAGES} \
    && pip install -r requirements.txt \
    && find /usr/local \
        \( -type d -a -name test -o -name tests \) \
        -o \( -type f -a -name '*.pyc' -o -name '*.pyo' \) \
        -exec rm -rf '{}' + \
    && runDeps="$( \
        scanelf --needed --nobanner --recursive /usr/local \
                | awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' \
                | sort -u \
                | xargs -r apk info --installed \
                | sort -u \
    )" \
    && apk add --virtual .rundeps $runDeps \
    && apk del --no-network .build-deps

VOLUME /usr/src/app

EXPOSE ${PyAlpine_PORT}