# Raspberry PI_Setup

## 消除開機彩屏
```Bash
sudo nano /boot/config.txt 
```
- 在config.txt中添加一行disable_splash=1，字面上的意思就是取消啟動界面


## 隱藏taskbar

1. 用終端機進到/etc/xdg/lxsession/LXDE-pi目錄
```Bash
cd /etc/xdg/lxsession/LXDE-pi
```
2. vim編輯autostart，並用sudo模式開啟
```Bash
sudo vim autostart 
``` 
3. 將@lxpanel --profile LXDE-pi使用#註解掉
```Bash
# @lxpanel --profile LXDE-pi
```
4. 樹梅派重新開機
```Bash
sudo reboot
```
## 隱藏滑鼠游標
1. 進到/etc/lightdm
```Bash
cd /etc/lightdm
```
2. vim編輯lightdm.conf，並用sudo模式開啟
```Bash
sudo vim lightdm.conf
```
3. 在lightdm.conf裡面增加xserver-command = X -nocursor
```Bash
xserver-command = X -nocursor
```
## Python預設版本

1. 進入”/usr/bin”目錄下，輸入ls -l | grep python顯示所有名字中包含python的檔案
```Bash
cd /usr/bin ; ls -l | grep python
```
2. 使用終端機指令進行版本設置
```Bash
sudo ln -sf python3 python
```
- ln修改符號連接
- -s軟體連接
- -f強制覆蓋現有連接

3. 用python –version 查看現在python版本
```Bash
python -version
```

###### tags: `Raspberry PI`