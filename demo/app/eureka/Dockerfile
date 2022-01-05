# 基于哪个镜像
FROM openjdk:8

# 复制文件到容器
COPY demo-1.0.0-SNAPSHOT.jar /app.jar

# 声明需要暴露的端口
EXPOSE 8080

# 配置容器启动后执行的命令
ENTRYPOINT ["java","‐jar","/app.jar"]