# mvn-repo
Android 使用github Maven 仓库

# 上传

在build.gradle增加代码

```
apply plugin: 'maven'
```

```
uploadArchives {
    repositories.mavenDeployer {
        repository(url: "file://你的github项目的本地根目录")
        pom.project {
            groupId “groupid”
            artifactId "artifactId"
            version "version
        }
    }
 }
```
然后运行


```
gradlew clean

gradlew uploadArchives

```

最近将生成的文件上传到github上即可


# 使用

在项目根build.gradle录添加代码

```
 repositories {
 
        maven { url 'https://raw.githubusercontent.com/github用户名/项目名/master' }
    }
```

在具体的项目build.gradle增加引用


```
implementation 'groupid:artifactId:version'
```

 

