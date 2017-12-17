# 基于Java 8镜像
FROM java:8

# 将本地文件夹挂载到当前容器
VOLUME /data/docker/configserver

# 复制文件到容器，也可以直接写成ADD config-server.jar /config-server.jar
ADD config-server.jar config-server.jar
RUN bash -c 'touch /config-server.jar'

# 声明需要暴露的端口
EXPOSE 8761

# 配置容器启动后执行的命令
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/config-server.jar"]

# 如果将此文件放置在jar文件同一目录下则使用此命令编译：
# docker build -t omni/config-server:0.0.1 .