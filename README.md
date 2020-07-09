![Logo](https://github.com/fluttify-project/fluttify-core-example/blob/develop/other/Logo-Landscape.png?raw=true)

# 网易云信 Flutter插件

[![pub package](https://img.shields.io/pub/v/nim_fluttify.svg)](https://pub.Flutter-io.cn/packages/nim_fluttify)

**专业版为付费插件, 如有需要请联系qq 382146139**

**专业版为付费插件, 如有需要请联系qq 382146139**

**专业版为付费插件, 如有需要请联系qq 382146139**

# Fluttify系列插件
|  名称  | 描述 | 仓库 |
|:-----:|:-----:|:-----:|
| [高德地图](https://github.com/fluttify-project/amap_map_fluttify)  |  高德地图地图组件, 提供地图控件 | [![pub package](https://img.shields.io/pub/v/amap_map_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_map_fluttify) |
| [高德定位](https://github.com/fluttify-project/amap_location_fluttify)  |  高德地图定位组件, 提供独立的定位功能 | [![pub package](https://img.shields.io/pub/v/amap_location_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_location_fluttify) |
| [高德搜索](https://github.com/fluttify-project/amap_search_fluttify)  |  高德地图搜索组件, 提供poi搜索等功能 | [![pub package](https://img.shields.io/pub/v/amap_search_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_search_fluttify) |
| [百度地图](https://github.com/fluttify-project/bmap_map_fluttify)  |  百度地图, 包含了地图控件, 定位以及搜索poi等功能 | [![pub package](https://img.shields.io/pub/v/bmap_map_fluttify.svg)](https://pub.Flutter-io.cn/packages/bmap_map_fluttify) |
| [百度人脸识别](https://github.com/fluttify-project/baidu_face_flutter)  |  百度人脸识别, 提供活体检测等功能 | [![pub package](https://img.shields.io/pub/v/baidu_face_flutter.svg)](https://pub.Flutter-io.cn/packages/baidu_face_flutter) |
| [网易直播](https://github.com/fluttify-project/netease_live_fluttify)  |  网易直播推流组件 | [![pub package](https://img.shields.io/pub/v/netease_live_fluttify.svg)](https://pub.Flutter-io.cn/packages/netease_live_fluttify) |
| [网易云信](https://github.com/fluttify-project/nim_fluttify)  |  网易云信 IM组件 | [![pub package](https://img.shields.io/pub/v/nim_fluttify.svg)](https://pub.Flutter-io.cn/packages/nim_fluttify) |
| [腾讯直播](https://github.com/fluttify-project/tencent_live_fluttify)  |  腾讯直播, 包含推流组件和播放组件 | [![pub package](https://img.shields.io/pub/v/tencent_live_fluttify.svg)](https://pub.Flutter-io.cn/packages/tencent_live_fluttify) |
| [腾讯IM](https://github.com/fluttify-project/tim_fluttify)  |  腾讯IM组件 | [![pub package](https://img.shields.io/pub/v/tim_fluttify.svg)](https://pub.Flutter-io.cn/packages/tim_fluttify) |
| [腾讯地图](https://github.com/fluttify-project/tmap_map_fluttify)  |  腾讯地图组件 | [![pub package](https://img.shields.io/pub/v/tmap_map_fluttify.svg)](https://pub.Flutter-io.cn/packages/tmap_map_fluttify) |
| [讯飞语音合成](https://github.com/fluttify-project/xftts_fluttify)  |  腾讯语言合成组件, 提供文字转语言功能 | [![pub package](https://img.shields.io/pub/v/xftts_fluttify.svg)](https://pub.flutter-io.cn/packages/xftts_fluttify) |
| [极光统计](https://github.com/fluttify-project/janalytics_fluttify)  |  极光统计组件, 提供异常上报等功能 | [![pub package](https://img.shields.io/pub/v/janalytics_fluttify.svg)](https://pub.flutter-io.cn/packages/janalytics_fluttify) |
| [阿里云RTC](https://github.com/fluttify-project/ali_rtc_fluttify)  |  阿里云实时音视频 | [![pub package](https://img.shields.io/pub/v/ali_rtc_fluttify.svg)](https://pub.flutter-io.cn/packages/ali_rtc_fluttify) |
| [环信](https://github.com/fluttify-project/easemob_im_fluttify)  |  环信IM | [![pub package](https://img.shields.io/pub/v/easemob_im_fluttify.svg)](https://pub.flutter-io.cn/packages/easemob_im_fluttify) |
| [未完待续...](https://github.com/fluttify-project)  |  如有其它需求, 请联系qq 382146139 | ![fluttify](https://img.shields.io/badge/fluttify-welcom-green) |

## 依赖
```yaml
dependencies:
  flutter:
    sdk: flutter
  nim_fluttify: ^x.x.x
```

## 配置
### Android
1. 在AndroidManifest.xml的application标签下配置app key:
```xml
<application>
    <meta-data
            android:name="com.netease.nim.appKey"
            android:value="6cxxxxxxxxxxxxxxxxxxxxxxxxxx9e" />
</application>
```
2. 由于SDK限制, 必须在Application中初始化, 所以需要重新指定Application的实现类, 需要用户继承`FlutterApplication`并重写`onCreate`方法, 然后在AndroidManifest.xml中配置自己实现的Application, 示例实现:
```java
import com.netease.nimlib.sdk.NIMClient;
import com.netease.nimlib.sdk.SDKOptions;

public class NIMApplication extends FlutterApplication {
    @Override
    @CallSuper
    public void onCreate() {
        super.onCreate();
        SDKOptions options = new SDKOptions();
        NIMClient.config(this, null, options);
    }
}
```
最终的AndroidManifest.xml中, 至少需要包含如下信息:
```xml
<application android:name="NIMApplication">
    <meta-data
            android:name="com.netease.nim.appKey"
            android:value="6cxxxxxxxxxxxxxxxxxxxxxxxxxx9e" />
</application>
```
3. 云信最低支持minSdk为17, Flutter默认为16, 所以需要修改app/build.gradle下的minSdkVersion为17.
```groovy
android {
    defaultConfig {
        minSdkVersion 17 // 原本为16, 改为17
    }
}
```
4. AndroidManifest.xml不需要用户再声明权限和官方提及的组件, 已经在插件中声明;
5. 不需要再配置混淆规则, 已在插件中配置混淆规则;

### iOS
1. 选择图片时需要配置访问相册的权限, 在Info.plist中添加相册权限:
```xml
<key>NSPhotoLibraryUsageDescription</key>
<string>需要相册权限</string>
```
2. Flutter默认的最低支持版本是iOS 8.0, 云信的最低支持版本是iOS 9.0. 所以需要更改Podfile:
```ruby
# Uncomment this line to define a global platform for your project
# platform :ios, '9.0'
```
改为(即去掉注释)
```ruby
# Uncomment this line to define a global platform for your project
platform :ios, '9.0'
```

## 导入
```dart
import 'package:nim_fluttify/nim_fluttify.dart';
```

## 使用
插件的主要类为Nim类, Nim类为单例, 调用时使用`Nim.instance.xxx`来使用. 具体请参考[wiki](https://github.com/fluttify-project/netease_im_fluttify/wiki).

## 社区
| QQ2群 | QQ1群(已满) |
| :----------: | :----------: |
| 加入QQ群讨论 <br/> <img src="https://github.com/fluttify-project/fluttify-project/blob/master/resources/qrcode_1593774649831.jpg?raw=true" height="300"> |加入QQ群讨论 <br/> <img src="https://github.com/fluttify-project/fluttify-project/blob/master/resources/1593774713224_temp_qrcode_share_9993.png?raw=true" height="300"> | 

## 社区版与专业版
|   登录登出  | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  登录  |  ✅ |  ✅   |
|  登出  |  ✅ |  ✅   |
|  在线状态监听  |  ✅ |  ✅   |

| 消息收发 | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  消息监听  |  ✅ |  ✅   |
|  发送文字消息  |  ✅ |  ✅   |
|  发送图片消息  |  ✅ |  ✅   |
|  发送音频消息  |  ✅ |  ✅   |
|  发送视频消息  |  ✅ |  ✅   |
|  发送文件消息  |  ✅ |  ✅   |
|  发送位置消息  |  ✅ |  ✅   |
|  发送自定义消息  |  ✅ |  ✅   |

| 用户关系托管 | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  获取我的好友列表  |  ✅ |  ✅   |
|  获取免打扰列表  |  ✅ |  ✅   |
|  请求添加好友  |  ✅ |  ✅   |
|  删除好友  |  ✅ |  ✅   |
|  处理添加好友申请(同意/拒绝)  |  ✅ |  ✅   |
|  判断用户是好友  |  ✅ |  ✅   |
|  加入黑名单  |  ✅ |  ✅   |
|  移出黑名单  |  ✅ |  ✅   |
|  判断用户是否在黑名单  |  ✅ |  ✅   |
|  判断用户是免打扰  |  ✅ |  ✅   |
|  获取黑名单列表  |  ✅ |  ✅   |
|  是否接收用户[account]的消息  |  ✅ |  ✅   |

| 聊天室 | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  进入聊天室  |  ✅ |  ✅   |
|  退出聊天室  |  ✅ |  ✅   |
|  获取聊天室信息  |  ✅ |  ✅   |
|  聊天室状态监听  |  ✅ |  ✅   |
|  聊天室踢出状态监听  |  ✅ |  ✅   |

| 最近会话 | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  获取会话列表  |  ✅ |  ✅   |

| 历史记录 | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  查询消息历史  |  ✅ |  ✅   |

| 用户资料托管 | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  获取用户资料  |  ☑️ |  ✅   |

| 系统消息 | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  系统消息监听  |  ☑️ |  ✅   |

| 群组 | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  创建群组  |  ☑️ |  ✅   |
|  设置群聊消息提醒类型  |  ☑️ |  ✅   |
|  获取所有的群组  |  ☑️ |  ✅   |
|  查询群组资料  |  ☑️ |  ✅   |
|  踢人出群  |  ☑️ |  ✅   |
|  主动退群  |  ☑️ |  ✅   |
|  解散群  |  ☑️ |  ✅   |
|  获取群组成员列表  |  ☑️ |  ✅   |
|  查询被禁言群成员  |  ☑️ |  ✅   |
|  移除管理员  |  ☑️ |  ✅   |
|  提升管理员  |  ☑️ |  ✅   |
|  根据群 ID 和成员帐号获取群成员  |  ☑️ |  ✅   |
|  群成员禁言  |  ☑️ |  ✅   |
|  群整体禁言  |  ☑️ |  ✅   |
|  验证入群申请  |  ☑️ |  ✅   |
|  接受入群邀请  |  ☑️ |  ✅   |
|  拒绝入群邀请  |  ☑️ |  ✅   |
|  邀请加入群组  |  ☑️ |  ✅   |
|  转让群组  |  ☑️ |  ✅   |
|  用户申请加入群  |  ☑️ |  ✅   |

## LICENSE
> Copyright (C) 2020 yohom
> 
> This program is free software: you can redistribute it and/or modify
> it under the terms of the GNU General Public License as published by
> the Free Software Foundation, either version 3 of the License, or
> (at your option) any later version.
> 
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.
> 
> You should have received a copy of the GNU General Public License
> along with this program.  If not, see <https://www.gnu.org/licenses/>.
