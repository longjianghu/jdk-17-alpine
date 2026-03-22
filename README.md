### 项目说明

JDK 运行基础镜像，基于 Amazon Corretto Alpine 镜像构建，更改时区为上海。

- `17`: 基于 amazoncorretto:17-alpine3.18-jdk
- `17-fonts`: 17 版本基础上增加字体支持
- `21`: 基于 amazoncorretto:21-alpine3.22-jdk
- `21-fonts`: 21 版本基础上增加字体支持

### 镜像特性

- 使用非 root 用户（appuser）运行，提升安全性
- 时区设置为 Asia/Shanghai
- 使用阿里云镜像源加速
- 清理构建缓存，减小镜像体积

### 构建容器

```bash
docker build -t longjianghu/jdk:17 ./17

docker build -t longjianghu/jdk:17-fonts ./17-fonts

docker build -t longjianghu/jdk:21 ./21

docker build -t longjianghu/jdk:21-fonts ./21-fonts
```

### Docker 镜像

```bash
docker pull longjianghu/jdk:17

docker pull longjianghu/jdk:21
```

### 使用说明

- `longjianghu/jdk:17`: JDK 17 基础镜像，指定时区为上海
- `longjianghu/jdk:17-fonts`: 17 版本基础上安装ttf-dejavu和font-terminus字体，适用于需要生成验证码的场景
- `longjianghu/jdk:21`: JDK 21 基础镜像，指定时区为上海
- `longjianghu/jdk:21-fonts`: 21 版本基础上安装ttf-dejavu和font-terminus字体，适用于需要生成验证码的场景