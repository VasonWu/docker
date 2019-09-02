# 在logstash中安装json_lines插件

## 运行Docker
```
docker-compose up -d
```

## 安装logstash插件

```
# 进入logstash容器
docker exec -it logstash /bin/bash
# 进入bin目录
cd /bin/
# 安装插件
logstash-plugin install logstash-codec-json_lines
# 退出容器
exit
# 重启logstash服务
docker restart logstash
```

## 其他
### 设置了动态创建index
```
output { 
    elasticsearch {   
        hosts => "es:9200"   
        index => "%{[appname]}" 
    }
}
```
```
<encoder charset="UTF-8" class="net.logstash.logback.encoder.LogstashEncoder">   
    <customFields>{"appname":"xxx"}</customFields>
</encoder>
```


## 参考
[
SpringBoot应用整合ELK实现日志收集](https://macrozheng.github.io/mall-learning/#/technology/mall_tiny_elk?id=springboot应用整合elk实现日志收集)

