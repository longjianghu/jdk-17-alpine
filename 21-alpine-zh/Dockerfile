FROM amazoncorretto:21-alpine3.22-jdk

LABEL maintainer="Longjianghu <215241062@qq.com>"
LABEL description="Alpine JDK 21 base image with Asia/Shanghai timezone, Terminus font, and non-root user."

ARG TIMEZONE=Asia/Shanghai

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && \
    apk add --no-cache \
        tzdata \
        fontconfig \
        ttf-dejavu \
        font-terminus \
        curl && \
    ln -snf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && \
    echo "${TIMEZONE}" > /etc/timezone && \
    fc-cache -fv && \
    addgroup -S appgroup && adduser -S appuser -G appgroup

WORKDIR /app

USER appuser

CMD ["sh"]