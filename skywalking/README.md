
# Skywalking 教程

## 1. 部署
```
docker-compose up -d
```

## 2. 集成Spring Boot
2.1 下载Java Agent
选择最新版本：6.3.0 （老版本不支持JDK11、12）
https://skywalking.apache.org/downloads/

解压后找到agent目录

启动时添加参数：
```
java -javaagent:<skywalking-agent-path> -Dskywalking.agent.service_name=<ServiceName> -jar yourApp.jar
```

## 3. 参考
* https://github.com/JaredTan95/skywalking-docker/blob/master/6.x/docker-compose/docker-compose.yml

## 4. Tips
* 目前的版本6.3.0没有登录功能，部署需要通过其他方式对服务进行防护，避免信息泄露


