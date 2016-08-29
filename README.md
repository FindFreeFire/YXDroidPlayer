## 云犀直播 Player 控件 , 官方API说明
-  @author  FindFreeFire <1719048237@qq.com> 
-  @link 
-  @version 1.0 

YXPlayerKit 是一个基于 PLPlayerKit 适用于 iOS 的音视频播放器 SDK，可高度定制化和二次开发，特色是支持 RTMP 和 HLS 直播流媒体播放。
- 相关API网站 ：http://b.test.yunxi.tv/developer/


### 1.功能特性
- [x] RTMP 直播流播放
- [x] HLS 播放
- [x] 高可定制
- [x] 音频后台播放
- [x] RTMP 直播首屏秒开支持
- [x] RTMP 直播累积延迟消除技术

### 2.快速配置

#### 1.添加权限
在 AndroidMainfest 添加网络访问权限
<uses-permission android:name="android.permission.INTERNET" />

#### 2.配置工程
将 yunxi_player.aar 文件拷贝到项目目录下的libs文件下

#### 3.布局文件
```xml
 <com.yunxi.player.lib.YXPlayer
                android:id="@+id/yunxi_player"
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:layout_gravity="center"
                android:orientation="vertical"></com.yunxi.player.lib.YXPlayer>
```
#### 4.注册SDK
 
```java
       YXSDK.register(APPID);    //注册信息 填入APPID
```
    
#### 5.初始化播放器
   
```java
      yunxiPlayer.init(this, livestreamJson, loadingDrawable);     //初始化视频播放器
```
#### 6.各个生命周期配置 
```java
    @Override
    protected void onResume() {
        super.onResume();
        yunxiPlayer.resumePlay();
    }

    @Override
    protected void onPause() {
        super.onPause();
        yunxiPlayer.pausePlayer();
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        yunxiPlayer.onDestory();
    } 
    
```
### 3.控制方法
#### 1.开始直播
   
```java
      yunxiPlayer.startPlayer();
```  
#### 2.停止直播
   
```java
      yunxiPlayer.stopPlayer();
```  

#### 3.判断当前是否在直播中
   
```java
       yunxiPlayer.isPlaying();
```  
  
