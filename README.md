# zline root pom

定义了一些需要用到的第三方库版本，如果有版本不满足需求的或者需要新增库，请直接提 Merge Request

## 使用方式

1.直接拷贝 settings.xml 到 ~/.m2/settings.xml 即可

2.在其他项目中继承该 pom 即可

```
    <parent>
        <groupId>com.line0</groupId>
        <artifactId>zline-root</artifactId>
        <version>${version}</version>
    </parent>
```
