# Make_Rpi_OsLite

## 使用的OsLite檔案

網址: https://www.tomshardware.com/how-to/back-up-raspberry-pi-as-disk-image

---
## Backup Raspberry Pi as a Disk Image

```typescript
sudo dd if=/dev/sdb of=~/Desktop/eGGi_OSLite_X_20211118.img bs=1M count=6000
```
```typescript
sudo dd if=/dev/sdb of=~/Desktop/eGGi_OSLite_X_20211118.img bs=1M count=6000
```
---
##  quite startup
```typescript
sudo nano  /boot/cmdline.txt
```
### Change
```typescript
logo.nologo consoleblank=0 loglevel=1 quiet
```
---
## REMOVE THE TEXTS AND LOGO

```typescript
sudo nano /boot/config.txt
```
- Write this in your terminal and open  /boot/config.txt, add “disable_splash=1” to remove the color test/rainbow screen. Now write
```typescript
sudo nano /boot/cmdline.txt
```
- At the end of the line add “logo.nologo” for removing the Raspberry logo.Disable the commands and various bits of the kernel by adding “consoleblank=0 loglevel=1 quiet” next to “logo.nologo”. Make sure everything is in one line. After that press ctrl+X, Y for save and Enter to return to the command line.Now remove the login prompt by running

```typescript
sudo systemctl disable getty@tty3
```

## ADDING NEW SPLASH SCREEN
- Now place the desired picture as your new splash screen. To make the image readable install fbi, the image reader and the framebuffer. For installation write

```typescript
sudo apt install fbi
```
- It will take a few seconds to install. After this we have to create a file by
```typescript
sudo nano /etc/systemd/system/splashscreen.service
```
## REBOOT YOUR PI

### Enable your service by running 
```typescript
sudo apt-get update
sudo systemctl enable splashscreen
sudo systemctl disable splashscreen
```
### Now reboot the Raspberry Pi and verify your image by
```typescript
sudo reboot
```
###### tags: `Raspberry PI`