# 一.Xposed检测工具下载
https://github.com/android-hacker/VirtualXposed
# 二.合规检测模块 即当前项目打包的apk 可以修改HookTrack增加检测的方法
check_module.apk
# 三.检测流程
https://blog.csdn.net/wang_yong_hui_1234/article/details/125087621

1. 安装 VirtrulXposed.apk (VirtualXposed_0.20.3-64.apk 64位 推荐(问题比较少)，VirtualXposed_0.18.2-x86.apk 32位(问题比较少) 其他VirtualXposed_0.22.0-Android12.apk支持Android 12(低版本手机安装App会崩溃))
2. 安装check_module.apk和需要检测的apk
3. 打开进入VirtrulXposed，点击底部白色按钮，点击列表中“添加应用”，添加check_module.apk和需要检测的apk
4. 点击“模块管理”勾选安装的模块 check_module，（可选步骤：可以杀死VirtrulXposed虚拟机重新打开）
5. 回到底部有白色按钮的页面，然后上划，进入应用页面，打开Xposed app，打开check_module app
6. 再打开Xposed app清理一下日志，然后再打开需要检测的app，在隐私协议弹窗页面，不要点同意，操作一下其他非同意的按钮
7. 查看日志检测是否有违规
   * 打开Xposed app查看日志
   * 或者是通过命令查看比较实时
   ```
    adb logcat | grep -i " Xposed  :" | grep [包名] 
    或者
    adb logcat | grep -i "secheguicheck" | grep [包名]
   ```


# 由[ChenJunsen/Hegui3.0]( https://github.com/ChenJunsen/Hegui3.0)项目 改版而来
增加了几个hook的点以及log打印的字符串，方便logcat中筛选
安装配置好此插件后通过命令查看比较实时
```
adb logcat | grep -i " Xposed  :" | grep [包名] 
或者
adb logcat | grep -i "secheguicheck" | grep [包名] 

例如：adb logcat | grep -i " Xposed  :" | grep com.vpgame.eric
```

