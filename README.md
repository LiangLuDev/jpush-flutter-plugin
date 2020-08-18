[![QQ Group](https://img.shields.io/badge/QQ%20Group-862401307-red.svg)]()
# JPush Flutter Plugin

### 安装

在工程 pubspec.yaml 中加入 dependencies

```
  
//github  集成
dependencies:
  jpush_flutter:
    git:
      url: git://github.com/jpush/jpush-flutter-plugin.git
      ref: master
      
// pub 集成
dependencies:
  jpush_flutter: 0.5.6
```

### 配置

##### Android:

在 `/android/app/build.gradle` 中添加下列代码：

```groovy
android: {
  ....
  defaultConfig {
    applicationId "替换成自己应用 ID"
    ...
    ndk {
	//选择要添加的对应 cpu 类型的 .so 库。
	abiFilters 'armeabi', 'armeabi-v7a', 'x86', 'x86_64', 'mips', 'mips64', 'arm64-v8a',        
    }

    manifestPlaceholders = [
        JPUSH_PKGNAME : applicationId,
        JPUSH_APPKEY : "appkey", // NOTE: JPush 上注册的包名对应的 Appkey.
        JPUSH_CHANNEL : "developer-default", //暂时填写默认值即可.
    ]
  }    
}
```

##### iOS:

- 由于在Flutter 1.17 - 1.20 版本无法通过编译，因此放弃在iOS上的推送，删除相关代码，采用原生。

### APIs

**注意** : 需要先调用 JPush.setup 来初始化插件，才能保证其他功能正常工作。

 [参考](./documents/APIs.md)

