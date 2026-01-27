### 项目说明

JDK17 运行基础镜像,基于amazoncorretto:17-alpine3.18-jdk镜像，更改时区为上海。


### 构建容器

docker build -t longjianghu/jdk:17 ./

docker build -t longjianghu/jdk:17-alpine-zh ./17-alpine-zh

docker build -t longjianghu/jdk:21 ./21

docker build -t longjianghu/jdk:21-alpine-zh ./21-alpine-zh

### Docker 镜像

docker pull longjianghu/jdk:17

### 使用说明

longjianghu/jdk:17 指定时区为上海

longjianghu/jdk:171 相比 longjianghu/jdk:17 版本安装了字体库，适用于需要生成验证码的场景。