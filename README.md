# ライブ・ア・ヒーロー！ Mod
* 修改战斗相关功能
* 如果没有显示“注入完成”，可以设置1000毫秒这样的延迟
* 只能真实机器，模拟器需要框架本身的frida支持了才行

## 基础功能
* 我方锁血、技能消耗全为0

## 可选功能
* 游戏速度修改，在主界面左上方点击“お知らせ”图片切换，在1倍、3倍、5倍之间切换
* 战斗开场不动直接胜利，在主界面点击“お知らせ”按钮开关
* 进了战斗想开直接胜利可以连点4次“紫色沙漏”图标

## 免root相关
### 黑盒方法：
#### 首次执行：
1. 安装JsHook
2. 安装黑盒，一般来说安装BlackBox64 https://github.com/FBlackBox/BlackBox/releases
3. 打开BlackBox64 -> 右上角三点 -> 软件设置 启动Xposed框架 -> 模块管理 -> 勾选JsHook -> 关闭BlackBox64
4. 打开BlackBox64 -> 点+ -> LiveAHero -> 进入游戏提示下载后关闭
5. 外部使用文件应用，如MT管理器，把 手机内部存储/Android/data/jp.co.lifewonders.liveahero/files/datas/userkey 复制到 手机内部存储/Android/data/top.niunaijun.blackboxa64/files/blackbox/storage/emulated/0/Android/data/jp.co.lifewonders.liveahero/files/datas/userkey
6. 打开BlackBox64 -> 打开JsHook -> 框架管理 -> 安装FridaMod
7. 打开BlackBox64 -> 打开JsHook -> 仓库 -> 下载脚本
8. 打开BlackBox64 -> 打开JsHook -> 应用 -> LiveAHero -> 启动Hook服务 -> 启动配置(脚本配置) -> 延时设置1000 -> 选择注入框架“FridaMod” -> 启动下载的脚本 -> 运行游戏
9. 弹出“不支持Google Play服务”提示可以无视，实在不想看到可以BlackBox64安装以下3个APK解决
* https://github.com/xkeyC/x_google_installer/releases/tag/api28
* https://github.com/xkeyC/x_google_installer/releases/tag/s212417037
* https://github.com/xkeyC/x_google_installer/releases/tag/st82601710
#### 游戏更新后：
* 应该在外部更新游戏就行了？

### 普通方法：
#### 首次执行：
1. 安装JsHook
2. **先引继帐号**，**先引继帐号**，**先引继帐号**，用手机自带的备份应用，或同品牌手机换机备份到另一台手机
3. 备份userkey，要在引继后备份，路径是 手机内部存储/Android/data/jp.co.lifewonders.liveahero/files/datas/userkey
4. JsHook -> 应用 -> LiveAHero -> 注入Hook服务 -> 卸载再安装 -> 先不要启动Hook，把 **帐号引继** 或者 **进入主界面关闭游戏，覆盖userkey** 完成后，进入主界面确认是之前的账号，再启动Hook
#### 游戏更新后：
1. 用QooApp之类的下载游戏最新安装包
2. QooApp的下载的安装包路径为 手机内部存储/Android/data/com.qooapp.qoohelper/files/Download/game/jp.co.lifewonders.liveahero
3. JsHook -> 安装包注入Hook服务 -> 选择下载的安装包 -> 安装 -> 启动
  
## 预览
![image](https://i.imgur.com/eiX2Jp0.jpg)
