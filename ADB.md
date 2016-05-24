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

Wireless usage

adb is usually used over USB. However, it is also possible to use over Wi-Fi, as described here.

1. Connect your Android device and adb host computer to a common Wi-Fi network accessible to both. We have found that not all access points are suitable; you may need to use an access point whose firewall is configured properly to support adb. Note: If you are attempting to connect to a Wear device, force it to connect to Wi-Fi by shutting off Bluetooth on the phone connected to it.


2. Connect the device to the host computer with a USB cable.


3. Set the target device to listen for a TCP/IP connection on port 5555.                                                    
      $ adb tcpip 5555 


4. Disconnect the USB cable from the target device.


5. Find the IP address of the Android device. For example, on a Nexus device, you can find the IP address at Settings > About tablet (or About phone) > Status > IP address. Or, on an Android Wear device, you can find the IP address at Settings > Wi-Fi Settings > Advanced > IP address.



6. Connect to the device, identifying it by IP address.        
      $ adb connect <device-ip-address>    


7.  Confirm that your host computer is connected to the target device:                                                             $ adb devices                                                               
      List of devices attached                         
      <device-ip-address>:5555 device

#### Filter by tagname in Logcat

```sh
$ adb logcat -s TAG_NAME
$ adb logcat -s TAG_NAME_1 TAG_NAME_2
```

#### Filter by priority in Logcat

```sh
$ adb logcat "*:<priority>"
# Where <priority> can be V (Verbose), D (Debug), I (Info), W (Warning), E (Error), F (Fatal), S (Silent).
```

It can be combined with tagname command, to filter by tagname and priority
```sh
$ adb logcat -s TEST: W
```

#### Filter using grep in Logcat

```sh
$ adb logcat | grep "term"
$ adb logcat | grep "term1\|term2"
````

#### Find out processor version on Android Device (check if it's an ARM, for example)

```sh
$ adb shell cat /proc/cpuinfo
```
