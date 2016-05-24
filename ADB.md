#### View connected device

```sh
$ adb devices
```

If multiple devices are attached, use `adb -s DEVICE_ID` to target a specific device

<a name="list_running_services">
#### List of running services

```sh
$ adb shell dumpsys activity services
```

#### Install an app in the connected device

```sh
$ adb -s xxx.xxx.xx.xxx:5555 install Downloads/com.xxx.android.2.8.0.apk
```

#### Copy file to the connected device

```sh
$ adb push Downloads/test-copy.rtf /sdcard/test-copy.txt
```

#### Fetch file from connected device

```sh
$ adb pull /sdcard/foo.txt Downloads/acd.txt
```

#### Start a remote shell

```sh
$ adb -s xxx.xxx.xx.xxx:5555 shell
```

#### Issuing single command without entering remote shell

```sh
$ adb shell ls /system/bin
```

#### Issuing monkey command

```sh
$ adb shell monkey -v -p com.xxxx.android 400
```

*Monkey is a program that runs on your emulator/device and generates random streams of user events such as clicks, touches, or gestures in the app.*

#### View log of system messages

```sh
$ adb logcat
```
