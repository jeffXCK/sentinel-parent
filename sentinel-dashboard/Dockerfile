# 基础镜像使用jdk8
FROM openjdk:8-jre
# 作者
MAINTAINER xck (xiaochangkun@126.com)

#定义时区参数
ENV TZ=Asia/Shanghai \
    USERNAME=sentinel \
    PASSWORD=sentinel \
    NACOS_ADDRESS=localhost:8848 \
    NACOS_NAMESPACE=""

# 指定容器内的时区
RUN cp /usr/share/zoneinfo/$TZ /etc/localtime && echo "$TZ" > /etc/timezone

COPY target/sentinel-dashboard.jar /app.jar

EXPOSE 8858

ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]
