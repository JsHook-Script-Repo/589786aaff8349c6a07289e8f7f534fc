# ライブ・ア・ヒーロー！ Mod
* 修改战斗相关功能
* 如果没有显示`注入完成`，可以设置1000毫秒这样的延迟
* 只能真实机器，模拟器需要框架本身的frida支持了才行

## 基础功能
* 我方锁血、技能消耗全为0

## 可选功能
* 游戏速度修改，在主界面左上方点击`お知らせ`图片切换，在1倍、3倍、5倍之间切换
* 战斗开场不动直接胜利，在主界面下方点击`お知らせ`按钮开关
* 进了战斗想开直接胜利可以连点4次`紫色沙漏`图标

## 免root相关
### 黑盒方法：
#### 首次执行：
1. 安装`JsHook`
2. 安装黑盒，一般来说安装`BlackBox64` https://github.com/FBlackBox/BlackBox/releases
3. 打开`BlackBox64` -> 右上角三点 -> 软件设置 -> **开启进程守护（防止闪退）** -> 启动Xposed框架 -> 模块管理 -> 勾选`JsHook` -> 关闭`BlackBox64`
4. 如果`BlackBox64`的软件设置的`GMS管理`能开启，则开启
5. 打开`BlackBox64` -> 点+ -> LiveAHero -> 进入游戏提示下载后关闭
6. 外部使用文件管理应用，如`MT管理器`，把
```
sdcard/Android/data/jp.co.lifewonders.liveahero/files/datas/userkey
```
复制到
```
sdcard/Android/data/top.niunaijun.blackboxa64/files/blackbox/storage/emulated/0/Android/data/jp.co.lifewonders.liveahero/files/datas/userkey
```
7. 上一步也可以直接把
```
sdcard/Android/data/jp.co.lifewonders.liveahero
```
整个文件夹复制到
```
sdcard/Android/data/top.niunaijun.blackboxa64/files/blackbox/storage/emulated/0/Android/data/jp.co.lifewonders.liveahero
```
8. 打开`BlackBox64` -> 打开`JsHook` -> 框架管理 -> 安装FridaMod
9. `JsHook`回首页 -> 仓库 -> 下载脚本
10. `JsHook`回首页 -> 应用 -> LiveAHero -> 启动Hook服务 -> 启动配置（脚本配置） -> 延时设置1000 -> 选择注入框架`FridaMod` -> 启动下载的脚本
11. 重启`BlackBox64` -> 运行游戏
12. `GMS管理`无法开启会弹出`不支持Google Play服务`提示，可以无视，实在不想看到可以`BlackBox64`手动选择安装以下3个APK解决（谷歌三件套）
* https://github.com/xkeyC/x_google_installer/releases/tag/api28
* https://github.com/xkeyC/x_google_installer/releases/tag/s212417037
* https://github.com/xkeyC/x_google_installer/releases/tag/st82601710
#### 游戏更新后：
* 外部更新游戏就行了，黑盒内部直接链接外部的应用的

### 普通方法：
#### 首次执行：
1. 安装`JsHook`
2. **先引继帐号**，**先引继帐号**，**先引继帐号**，用手机自带的备份应用，或同品牌手机换机备份到另一台手机
3. 备份`userkey`，要在引继后备份，路径是
```
sdcard/Android/data/jp.co.lifewonders.liveahero/files/datas/userkey
```
4. `JsHook` -> 应用 -> LiveAHero -> 注入Hook服务 -> 卸载再安装 -> 先不要启动Hook，把 **帐号引继** 或者 **进入主界面关闭游戏，覆盖userkey** 完成后，进入主界面确认是之前的账号，再启动Hook
#### 游戏更新后：
1. 用`QooApp`之类的下载游戏最新安装包
2. `QooApp`的下载的安装包路径为`sdcard/Android/data/com.qooapp.qoohelper/files/Download/game/jp.co.lifewonders.liveahero`
3. `JsHook` -> 安装包注入Hook服务 -> 选择下载的安装包 -> 安装 -> 启动
  
## 预览
![image](https://i.imgur.com/eiX2Jp0.jpg)
