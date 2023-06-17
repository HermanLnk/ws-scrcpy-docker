# Install Docker and Docker-Compose on OpenWrt
```
opkg update && opkg install docker luci-app-dockerman docker-compose dockerd
reboot
```

# OpenWrt ARM64

* https://hub.docker.com/r/haris132/ws-scrcpy/
* https://github.com/Haris131/ws-scrcpy-docker/

```
docker run --name ws-scrcpy -d -p 8000:8000 haris132/ws-scrcpy
docker exec ws-scrcpy adb connect android.device.ip:5555
```

# Docker image of ws scrcpy

Used to control Android devices in the browser.

* https://hub.docker.com/r/scavin/ws-scrcpy/
* https://github.com/scavin/ws-scrcpy-docker/

## use AMD64

```
docker run --name ws-scrcpy -d -p 8000:8000 scavin/ws-scrcpy
docker exec ws-scrcpy adb connect android.device.ip:5555
```

Pay attention to modify android.device.ip to the IP address of the Android device.

## Turn on adb over Wi-Fi for Android devices

1. Install the adb toolkit ([SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools))
2. Turn on developer mode
3. Connect the Android device using USB and authorize
4. Terminal input `adb tcpip 5555`

Just return `restarting in TCP mode port: 5555`.
Switch back to USB mode: `adb usb`

## reference link

* https://github.com/Genymobile/scrcpy
* https://github.com/NetrisTV/ws-scrcpy
* https://meta.appinn.net/t/topic/33828
* https://www.appinn.com/scrcpy-remote/  //Control Android with iPhone
