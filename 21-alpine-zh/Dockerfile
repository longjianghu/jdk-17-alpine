FROM amazoncorretto:21-alpine3.22-jdk

LABEL maintainer="Longjianghu <215241062@qq.com>"
LABEL description="Alpine JDK 21 base image with Asia/Shanghai timezone, Chinese fonts (WenQuanYi), and non-root user."
LABEL version="1.0"

ARG TIMEZONE=Asia/Shanghai

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && \
    apk update && apk add --no-cache \
        tzdata \
        fontconfig \
        ttf-dejavu \
        font-wqy-zenhei \
        curl && \
    rm -rf /var/cache/apk/* && \
    ln -snf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && \
    echo "${TIMEZONE}" > /etc/timezone && \
    fc-cache -fv && \
    addgroup -S appgroup && adduser -S appuser -G appgroup

WORKDIR /app

USER appuser

CMD ["sh"]