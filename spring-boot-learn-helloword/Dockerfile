#基础镜像
FROM openjdk:8-jdk-alpine

# 作者信息
MAINTAINER "zwj 1351072964@qq.com"

# 添加一个存储空间
#VOLUME /tmp

RUN apk add --no-cache tini

# 暴露8080端口
EXPOSE 8080

# 添加变量，如果使用dockerfile-maven-plugin，则会自动替换这里的变量内容
ARG JAR_FILE=target/spring-boot-learn-helloword-1.0.0-SNAPSHOT.jar

# 往容器中添加jar包
ADD ${JAR_FILE} app.jar

# 启动镜像自动运行程序
ENTRYPOINT ["/sbin/tini","--","java","-Djava.security.egd=file:/dev/urandom","-jar","/app.jar"]