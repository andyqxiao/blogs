Guoguo
  -trunk
  	 -vitamio
  	 -pullToRefreshViewsLibaray
     -src
     -assets
     -libs
      res
      .classpath
      .project
      AndroidManifest.xml
      project.properties
  +branches
  +tags

  svn:ignore
  .settings
  bin
  gen
  .DS_Store
  .idea
  build

1. so文件只上传armeabi和armeabi-v7a的，不支持mips和x86
2. 跨平台、无本地特殊配置，任何人签出代码后可以直接导入


目前的环境为：
Java: >=7
Eclipse: 4.5.x ADT: 23.0.x
Android Studio: >=1.4 (也可以使用1.5版本)
Android: targetSDK 6.0 build-tools 23.0.2

