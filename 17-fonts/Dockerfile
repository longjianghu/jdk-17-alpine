FROM amazoncorretto:17-alpine3.18-jdk

LABEL maintainer="longjianghu <215241062@qq.com>" \
      description="Alpine JDK 17 base image with Asia/Shanghai timezone and Terminus font."

ARG TIMEZONE=Asia/Shanghai

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
 && apk add --no-cache \
        tzdata \
        fontconfig \
        ttf-dejavu \
        font-terminus \
 && ln -snf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime \
 && echo "${TIMEZONE}" > /etc/timezone \
 && fc-cache -f

WORKDIR /app

# 仅供调试用，生产镜像会被 ENTRYPOINT 覆盖
CMD ["sh"]