# ライブ・ア・ヒーロー！ Mod
* 修改战斗相关功能
* rhino不能设置延迟，frida如果没有显示`注入完成`，可以设置1000毫秒这样的延迟
* 模拟器使用rhino，实机rhino和frida都行

## 基础功能
* 我方锁血、技能消耗全为0

## 可选功能
* 游戏速度修改，在主界面左上方点击`お知らせ`图片切换，在1倍、3倍、5倍之间切换
* 战斗开场不动直接胜利，在主界面下方点击`お知らせ`按钮开关
* 进了战斗想开直接胜利可以连点4次`紫色沙漏`图标

## 模拟器相关
* 拿`雷电9`举例，其他模拟器自己尝试
1. 先装好游戏能进入了，建议直接把手机的`sdcard/Android/data/jp.co.lifewonders.liveahero`整个打包，模拟器解压成一样路径，userkey也在里面了
2. 模拟器开好`ROOT`，设置`System.vmdk 可写入`
3. 装`Magisk Delta`的`Canary`版 https://huskydg.github.io/magisk-files/
4. 进入`Magisk Delta` -> 给`ROOT权限` -> 安装`Magisk` -> 方式选择`安装到系统分区` -> 重启模拟器 -> `Magisk Delta`设置打开`Zygisk`
5. 安装`JsHook` -> 安装`Magisk模块` -> 选择下载`LsposedMod-v1.0.12-1012-zygisk-release.zip` -> 到`Magisk Delta`的`模块`里`从本地安装` -> 选择安装下载的文件，重启模拟器
6. `JsHook` -> 仓库 -> 下载脚本
7. `JsHook` -> 应用 -> 龍脈R -> 启动Hook服务 -> 启动配置（脚本配置） -> 启动下载的脚本
8. 运行游戏，没有显示任何内容的话，自己随便编个js`common.toast('...')`看能不能显示，能显示再切回之前的脚本

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
