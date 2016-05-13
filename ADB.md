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

