## 通过 ADB 卸载系统应用

1. 开启 USB 调试模式
2. 连接电脑，安装 ADB
3. 打开终端，输入 `adb shell` 测试是否成功连接
4. 获取想要卸载的软件包名，输入 `pm uninstall -k --user 0 packageName` 来卸载应用
5. 获取包名可以通过在手机上打开软件，在终端输入 `dumpsys window | grep mCurrentFocus` 的方式来获取当前界面的信息，在输出信息中找到类似 `com.baidu.input_yijia` 这种以 `com` 开头的，就是软件的包名。
6. 也可以通过 `pm list packages | grep "keyword"` 开查找软件包。
7. 通过 `pm list` 可列出所有包名。