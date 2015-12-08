# LittleApple root pom

定义了一些需要用到的第三方库版本，如果有版本不满足需求的或者需要新增库，请直接提 Merge Request

## 使用方式

修改本地 hosts 文件， 增加

```
#littleapple host
127.0.0.1 maven.dev.littleapple.com

IP配置为maven nexus 部署的ip
nginx 配置maven.dev.littleapple.com IP和端口
使用nginx反向代理

在
server {
        listen       80 ;
        server_name  maven.dev.littleapple.com;

        location / {
            proxy_pass http://127.0.0.1:8081;
        }
    }

```


直接拷贝 settings.xml 到 ~/.m2/settings.xml 即可

或者在 ~/.m2/settings.xml 里增加

```
  <mirrors>
     <mirror>
      <id>loukou</id>
      <name>loukou central</name>
      <url>http://maven.dev.littleapple.com/nexus/content/groups/public/</url>
      <mirrorOf>*</mirrorOf>
    </mirror>
  </mirrors>
```

再在其他项目中继承该 pom 即可

```
    <parent>
        <groupId>com.littleapple</groupId>
        <artifactId>apple-root</artifactId>
        <version>${version}</version>
    </parent>
```
