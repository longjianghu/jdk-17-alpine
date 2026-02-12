FROM amazoncorretto:17-alpine3.18-jdk

LABEL maintainer="Longjianghu <215241062@qq.com>"
LABEL description="Alpine JDK 17 base image with Asia/Shanghai timezone, Chinese fonts (WenQuanYi), and non-root user."

ARG TIMEZONE=Asia/Shanghai

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && \
    apk update && apk add --no-cache \
        tzdata \
        fontconfig \
        ttf-dejavu \
        font-terminus \
        curl && \
    rm -rf /var/cache/apk/* && \
    ln -snf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && \
    echo "${TIMEZONE}" > /etc/timezone && \
    fc-cache -fv && \
    addgroup -S appgroup && adduser -S appuser -G appgroup

WORKDIR /app

USER appuser

CMD ["sh"]