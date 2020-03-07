# DigGradleDependencies

## 有什么用？

通常情况下，我们使用使用依赖库编译的时候，只是配置一下依赖就好了

```groovy
dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation 'androidx.appcompat:appcompat:1.1.0'
    implementation 'androidx.constraintlayout:constraintlayout:1.1.3'
}
```

但如果把`implementation`依赖的具体 aar 或者 jar 拷贝出来，就比较麻烦了，因为上面的依赖，内部可能还依赖其他的，使用本脚本就能解决这个问题。

## 如何使用？

```groovy
//先确保自己的 Project 能编译通过，然后引入 dig.gradle，有两种方式
//1:通过url引入（要确自己的网络能访问下面的地址）
apply from: 'https://raw.githubusercontent.com/andforce/DigGradleDependencies/master/dig.gradle'
//2:把 dig.gradle 拷贝到你自己的 Project 中
//apply from: '../dig.gradle'
```

配置完毕后，clean一下工程就能看到所有依赖的 aar 和 jar 了



![dig_clean](README.assets/dig_clean.gif)

