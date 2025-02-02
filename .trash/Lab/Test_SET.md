## Rules
- No pip install
## Update/Install software through Download file (Debian file)
```
sudo apt install ./<file>.deb
```
## Update Firefox (incase Notification reappear again)
```
sudo killall firefox
sudo snap refresh
```
## Install Flatpak for Appstore
```
sudo apt install flatpak
```
## Disable Auto Update Ubuntu
- [Disable Automatic Updates on Ubuntu 22.04 Jammy Jellyfish Linux - Linux Tutorials - Learn Linux Configuration](https://linuxconfig.org/disable-automatic-updates-on-ubuntu-22-04-jammy-jellyfish-linux)
## Setup Custom Shortcut for Launching Application
- *Settings/Keyboard > Keyboard Shortcuts: View and Customize Shortcuts > Custom Shortcuts* 
- Its required command to launch the applications
- command of specific app can be found under *Properties > Launcher > Command:*
- File path depend on AppStore Distributor
### Flatpak
```
/var/lib/flatpak/exports/share/applications
```
### Debian apt
```
/usr/share/applications/
```
### Snap
- Is Ubuntu Default, therefore only name of app in command is enough.
## General
### Get Adress of file
- Copy File
- Paste in Terminal
### Extension Manager
```
sudo apt install gnome-shell-extension-manager
```
### Improve Touchpad in X11/Xorg
- Full Guide: [How to Enable Touchpad Gestures in Ubuntu 22.04 on Xorg Session | UbuntuHandbook](https://ubuntuhandbook.org/index.php/2022/06/touchpad-gestures-ubuntu-22-04-xorg/)
```
sudo add-apt-repository ppa:touchegg/stable
sudo apt install touchegg
```
- *Extension > Browse > X11Gestures* 
### Speed up Startuptime
```
sudo apt install preload
```
### Reinstall
```bash
sudo apt install --reinstall input
```
### Backup System
- Timeshift
### Firewall
- firewall
### Cleanup Space
- Bleachbit
### Update and Upgrade ubuntu
```
sudo apt update && sudo apt upgrade 
```
### Update Snapstore
```
snap-store --quit && sudo snap refresh snap-store
```
### Mathlab
- [Install Matlab](https://www.youtube.com/watch?v=ZNHJkCo5sOc)
### Commandline history
- *Thunar > Home > View > Show Hidden Files > .bash_history*
### Quater Window snap
- *Extension > Tiling Assistant*
- To Disable: TIling Popup, Tile Groups
- Custom Shortcuts
	- ![](attachment/4b85fb33d5886e914c261b5c14216c8c.png)
### Install Command
```
sudo apt install package-one
```
### Uninstall Comand (App&Dependencies)
```
sudo apt-get purge <package name>
sudo apt-get autoremove --purge
```

```
sudo snap remove <package name>
```
### Create text file in File Manager (Thunar)
*RM > Create Document > Empty File* 
### Manage Startup Programm
- Full Guide: [Complete Guide for Managing Startup Applications in Ubuntu Linux: Learn to Add, Remove or Delay Startup Programs](https://itsfoss.com/manage-startup-applications-ubuntu/)
- find command of each apps in "Main Menu"
- Copy in "Startup Application"
- Show hidden Startup 
```
sudo sed -i "s/NoDisplay=true/NoDisplay=false/g" /etc/xdg/autostart/\*.desktop
```
- Hide hidden Startup 
```
sudo sed -i "s/NoDisplay=false/NoDisplay=true/g" /etc/xdg/autostart/\*.desktop
```
### Move file to permission required folder
Full Guide: [clipboard - How to copy files into /usr/local/? (permission denied) - Ask Ubuntu](https://askubuntu.com/questions/24952/how-to-copy-files-into-usr-local-permission-denied)
```
/usr/local/bin/
sudo -H nautilus
```

### Preview a File 
	sudo apt-get install gnome-sushi

### Remove RotationScreen
	sudo apt-get remove iio-sensor-proxy
### Stop RotationScreen
	sudo systemctl stop iio-sensor-proxy.service
	sudo systemctl disable iio-sensor-proxy.service


### Set a default Audio Output
	sudo -H gedit /etc/pulse/default.pa
	Comment out the line 
		load-module module-switch-on-connect
	restart puseaudio with 
		pulseaudio -k

### Change System File, Example
	sudo nano /etc/default/grub
	Find 
		GRUB_CMDLINE_LINUX_DEFAULT=”quiet splash”
	Change to
		GRUB_CMDLINE_LINUX_DEFAULT=”quiet intremap=nosid splash”
	Ctrl+O and Press Enter

### Airpod Bluetooth verbinden
	sudo nano /etc/bluetooth/main.conf
	Change "ControllerMode = bredr"
	sudo /etc/init.d/bluetooth restart
	
### Comma to Period DE Numpad
	sudo apt install gnome-tweak-tool
	Tweaks/Keyboard&Mouse/Additional Layout Options/Numeric Keypad...>Four level key with dot

### Maping Forward/Backward Mousebutton to Ubuntu File System
	Install
		sudo apt-get install xvkbd xbindkeys x11-utils
	Find the Mouse Button Codes 
		xev | grep ', button'

### Draw on Screen
	Extension/Draw On Your Screen 2
	
### Bring Focus to Cursor
	Jiggle/Default System
	
### Magnify Screen
	Settings/Acessibility	
### Larger Text
	Settings/Acessibility
	
### Display Keystrokes
- Screenkey
```
sudo apt-get -y install screenkey
Dont Support Wayland!!
```
### Create file inside folder
*Click 3Dots > Open Terminal inside Folder > Type command: cat > filename*
### Zip file
```
sudo apt-get install zip gzip tar
```
zip command
```
zip -r my_arch.zip my_folder
```
unzip command
```
unzip my_arch.zip
```
### Ordering/Organizing files by [[Nemo_DES]]
- Bulk rename
- Advance file search
### Hide Recycle Bin in Desktop
[Hide Trash Desktop Icon](https://ubuntuhandbook.org/index.php/2021/10/remove-trash-from-dock-ubuntu/)
	Install [[DconfEditor_DES]]
	search "org/gnome/shell/extensions/dash-to-dock"
	Turnoff show trash
	![](attachment/3902bd40a8f82c520dfc2837857c969a.png)


pdf=org.gnome.Evince.desktop;

[New bonus minimize window when click on icon](https://www.omgubuntu.co.uk/2021/07/enable-minimize-click-ubuntu-dock/amp) 
	Choose option: "Minize or Preview"
## Edit PDF & Image file
- [[PDF]]
## Default_mimeapps.list
- Default desktop app list, e.g. for .pdf, .mp4, or other common files
```
application/rtf=abiword.desktop
application/x-abiword=abiword.desktop
text/abiword=abiword.desktop
text/richtext=abiword.desktop
text/rtf=abiword.desktop
text/x-abiword=abiword.desktop
text/x-xml-abiword=abiword.desktop
x-content/blank-bd=brasero-nautilus.desktop
x-content/blank-dvd=brasero-nautilus.desktop
x-content/blank-cd=brasero-nautilus.desktop
x-content/blank-hddvd=brasero-nautilus.desktop
application/x-dia-diagram=dia.desktop
image/bmp=org.gnome.eog.desktop
image/gif=org.gnome.eog.desktop
image/jpeg=org.gnome.eog.desktop
image/jpg=org.gnome.eog.desktop
image/pjpeg=org.gnome.eog.desktop
image/png=org.gnome.eog.desktop
image/svg+xml=org.gnome.eog.desktop
image/svg+xml-compressed=org.gnome.eog.desktop
image/x-bmp=org.gnome.eog.desktop
image/x-gray=org.gnome.eog.desktop
image/x-icb=org.gnome.eog.desktop
image/x-ico=org.gnome.eog.desktop
image/x-pcx=org.gnome.eog.desktop
image/x-png=org.gnome.eog.desktop
image/x-portable-anymap=org.gnome.eog.desktop
image/x-portable-bitmap=org.gnome.eog.desktop
image/x-portable-graymap=org.gnome.eog.desktop
image/x-portable-pixmap=org.gnome.eog.desktop
image/x-xbitmap=org.gnome.eog.desktop
image/x-xpixmap=org.gnome.eog.desktop
image/vnd.wap.wbmp=org.gnome.eog.desktop
image/g3fax=gimp.desktop
image/x-compressed-xcf=gimp.desktop
image/x-fits=gimp.desktop
image/x-icon=gimp.desktop
image/x-psd=gimp.desktop
image/x-sgi=gimp.desktop
image/x-sun-raster=gimp.desktop
image/x-tga=gimp.desktop
image/x-xcf=gimp.desktop
image/x-xwindowdump=gimp.desktop
application/pdf=org.gnome.Evince.desktop
application/x-bzpdf=org.gnome.Evince.desktop
application/x-gzpdf=org.gnome.Evince.desktop
application/postscript=org.gnome.Evince.desktop
application/x-bzpostscript=org.gnome.Evince.desktop
application/x-gzpostscript=org.gnome.Evince.desktop
image/x-eps=org.gnome.Evince.desktop
image/x-bzeps=org.gnome.Evince.desktop
image/x-gzeps=org.gnome.Evince.desktop
application/x-dvi=org.gnome.Evince.desktop
application/x-bzdvi=org.gnome.Evince.desktop
application/x-gzdvi=org.gnome.Evince.desktop
image/vnd.djvu=org.gnome.Evince.desktop
image/tiff=org.gnome.Evince.desktop
application/x-cbr=org.gnome.Evince.desktop
application/x-cbz=org.gnome.Evince.desktop
application/x-cb7=org.gnome.Evince.desktop
text/calendar=org.gnome.Evolution.desktop
text/x-vcard=org.gnome.Evolution.desktop
application/mbox=org.gnome.Evolution.desktop
message/rfc822=org.gnome.Evolution.desktop
x-scheme-handler/mailto=org.gnome.Evolution.desktop
application/x-7z-compressed=org.gnome.FileRoller.desktop
application/x-7z-compressed-tar=org.gnome.FileRoller.desktop
application/x-ace=org.gnome.FileRoller.desktop
application/x-alz=org.gnome.FileRoller.desktop
application/x-ar=org.gnome.FileRoller.desktop
application/x-arj=org.gnome.FileRoller.desktop
application/x-bzip=org.gnome.FileRoller.desktop
application/x-bzip-compressed-tar=org.gnome.FileRoller.desktop
application/x-bzip1=org.gnome.FileRoller.desktop
application/x-bzip1-compressed-tar=org.gnome.FileRoller.desktop
application/x-cabinet=org.gnome.FileRoller.desktop
application/x-compress=org.gnome.FileRoller.desktop
application/x-compressed-tar=org.gnome.FileRoller.desktop
application/x-cpio=org.gnome.FileRoller.desktop
application/x-deb=org.gnome.FileRoller.desktop
application/x-ear=org.gnome.FileRoller.desktop
application/x-gtar=org.gnome.FileRoller.desktop
application/x-gzip=org.gnome.FileRoller.desktop
application/x-java-archive=org.gnome.FileRoller.desktop
application/x-lha=org.gnome.FileRoller.desktop
application/x-lhz=org.gnome.FileRoller.desktop
application/x-lzip=org.gnome.FileRoller.desktop
application/x-lzip-compressed-tar=org.gnome.FileRoller.desktop
application/x-lzma=org.gnome.FileRoller.desktop
application/x-lzma-compressed-tar=org.gnome.FileRoller.desktop
application/x-lzop=org.gnome.FileRoller.desktop
application/x-lzop-compressed-tar=org.gnome.FileRoller.desktop
application/x-rar=org.gnome.FileRoller.desktop
application/x-rar-compressed=org.gnome.FileRoller.desktop
application/x-rpm=org.gnome.FileRoller.desktop
application/x-rzip=org.gnome.FileRoller.desktop
application/x-tar=org.gnome.FileRoller.desktop
application/x-tarz=org.gnome.FileRoller.desktop
application/x-stuffit=org.gnome.FileRoller.desktop
application/x-war=org.gnome.FileRoller.desktop
application/x-xz=org.gnome.FileRoller.desktop
application/x-xz-compressed-tar=org.gnome.FileRoller.desktop
application/x-zip=org.gnome.FileRoller.desktop
application/x-zip-compressed=org.gnome.FileRoller.desktop
application/x-zoo=org.gnome.FileRoller.desktop
application/zip=org.gnome.FileRoller.desktop
multipart/x-zip=org.gnome.FileRoller.desktop
text/plain=org.gnome.gedit.desktop
text/css=org.gnome.gedit.desktop
text/javascript=org.gnome.gedit.desktop
text/mathml=org.gnome.gedit.desktop
text/x-c++hdr=org.gnome.gedit.desktop
text/x-c++src=org.gnome.gedit.desktop
text/x-csrc=org.gnome.gedit.desktop
text/x-chdr=org.gnome.gedit.desktop
text/x-dtd=org.gnome.gedit.desktop
text/x-java=org.gnome.gedit.desktop
text/x-javascript=org.gnome.gedit.desktop
text/x-makefile=org.gnome.gedit.desktop
text/x-moc=org.gnome.gedit.desktop
text/x-pascal=org.gnome.gedit.desktop
text/x-patch=org.gnome.gedit.desktop
text/x-perl=org.gnome.gedit.desktop
text/x-php=org.gnome.gedit.desktop
text/x-python=org.gnome.gedit.desktop
text/x-sql=org.gnome.gedit.desktop
text/x-tcl=org.gnome.gedit.desktop
text/x-tex=org.gnome.gedit.desktop
text/xml=org.gnome.gedit.desktop
application/javascript=org.gnome.gedit.desktop
application/x-cgi=org.gnome.gedit.desktop
application/x-javascript=org.gnome.gedit.desktop
application/x-perl=org.gnome.gedit.desktop
application/x-php=org.gnome.gedit.desktop
application/x-python=org.gnome.gedit.desktop
application/x-shellscript=org.gnome.gedit.desktop
application/xml=org.gnome.gedit.desktop
application/xml-dtd=org.gnome.gedit.desktop
application/x-font-ttf=org.gnome.font-viewer.desktop
application/x-font-pcf=org.gnome.font-viewer.desktop
application/x-font-type1=org.gnome.font-viewer.desktop
application/x-font-otf=org.gnome.font-viewer.desktop
application/x-gnumeric=gnumeric.desktop
application/tab-separated-values=gnumeric.desktop
text/tab-separated-values=gnumeric.desktop
text/csv=gnumeric.desktop
text/x-csv=gnumeric.desktop
application/vnd.lotus-1-2-3=gnumeric.desktop
application/x-123=gnumeric.desktop
application/x-applix-spreadsheet=gnumeric.desktop
application/x-mps=gnumeric.desktop
application/x-oleo=gnumeric.desktop
application/x-planperfect=gnumeric.desktop
application/x-quattropro=gnumeric.desktop
application/x-sc=gnumeric.desktop
application/x-sylk=gnumeric.desktop
application/x-xbase=gnumeric.desktop
text/html=firefox-esr.desktop;firefox.desktop;
application/xhtml+xml=firefox-esr.desktop;firefox.desktop;
application/rss+xml=firefox-esr.desktop;firefox.desktop;
application/rdf+xml=firefox-esr.desktop;firefox.desktop;
x-scheme-handler/http=firefox-esr.desktop;firefox.desktop;
x-scheme-handler/https=firefox-esr.desktop;firefox.desktop;
application/vnd.oasis.opendocument.spreadsheet=libreoffice-calc.desktop
application/vnd.oasis.opendocument.spreadsheet-flat-xml=libreoffice-calc.desktop
application/vnd.oasis.opendocument.spreadsheet-template=libreoffice-calc.desktop
application/vnd.sun.xml.calc=libreoffice-calc.desktop
application/vnd.sun.xml.calc.template=libreoffice-calc.desktop
application/msexcel=libreoffice-calc.desktop
application/vnd.ms-excel=libreoffice-calc.desktop
application/vnd.openxmlformats-officedocument.spreadsheetml.sheet=libreoffice-calc.desktop
application/vnd.ms-excel.sheet.macroenabled.12=libreoffice-calc.desktop
application/vnd.openxmlformats-officedocument.spreadsheetml.template=libreoffice-calc.desktop
application/vnd.ms-excel.template.macroenabled.12=libreoffice-calc.desktop
application/vnd.ms-excel.sheet.binary.macroenabled.12=libreoffice-calc.desktop
application/x-dbf=libreoffice-calc.desktop
text/spreadsheet=libreoffice-calc.desktop
application/vnd.oasis.opendocument.graphics=libreoffice-draw.desktop
application/vnd.oasis.opendocument.graphics-flat-xml=libreoffice-draw.desktop
application/vnd.oasis.opendocument.graphics-template=libreoffice-draw.desktop
application/vnd.sun.xml.draw=libreoffice-draw.desktop
application/vnd.sun.xml.draw.template=libreoffice-draw.desktop
application/vnd.visio=libreoffice-draw.desktop
application/vnd.oasis.opendocument.presentation=libreoffice-impress.desktop
application/vnd.oasis.opendocument.presentation-flat-xml=libreoffice-impress.desktop
application/vnd.oasis.opendocument.presentation-template=libreoffice-impress.desktop
application/vnd.sun.xml.impress=libreoffice-impress.desktop
application/vnd.sun.xml.impress.template=libreoffice-impress.desktop
application/mspowerpoint=libreoffice-impress.desktop
application/vnd.ms-powerpoint=libreoffice-impress.desktop
application/vnd.openxmlformats-officedocument.presentationml.presentation=libreoffice-impress.desktop
application/vnd.ms-powerpoint.presentation.macroenabled.12=libreoffice-impress.desktop
application/vnd.openxmlformats-officedocument.presentationml.template=libreoffice-impress.desktop
application/vnd.ms-powerpoint.template.macroenabled.12=libreoffice-impress.desktop
application/vnd.openxmlformats-officedocument.presentationml.slide=libreoffice-impress.desktop
application/vnd.openxmlformats-officedocument.presentationml.slideshow=libreoffice-impress.desktop
application/vnd.oasis.opendocument.formula=libreoffice-math.desktop
application/vnd.sun.xml.math=libreoffice-math.desktop
application/vnd.oasis.opendocument.text=libreoffice-writer.desktop
application/vnd.oasis.opendocument.text-flat-xml=libreoffice-writer.desktop
application/vnd.oasis.opendocument.text-template=libreoffice-writer.desktop
application/vnd.oasis.opendocument.text-web=libreoffice-writer.desktop
application/vnd.oasis.opendocument.text-master=libreoffice-writer.desktop
application/vnd.sun.xml.writer=libreoffice-writer.desktop
application/vnd.sun.xml.writer.template=libreoffice-writer.desktop
application/vnd.sun.xml.writer.global=libreoffice-writer.desktop
eapplication/vnd.ms-word=libreoffice-writer.desktop
application/x-doc=libreoffice-writer.desktop
application/x-hwp=libreoffice-writer.desktop
application/vnd.wordperfect=libreoffice-writer.desktop
application/wordperfect=libreoffice-writer.desktop
application/vnd.lotus-wordpro=libreoffice-writer.desktop
application/vnd.openxmlformats-officedocument.wordprocessingml.document=libreoffice-writer.desktop
application/vnd.ms-word.document.macroenabled.12=libreoffice-writer.desktop
application/vnd.openxmlformats-officedocument.wordprocessingml.template=libreoffice-writer.desktop
application/vnd.ms-word.template.macroenabled.12=libreoffice-writer.desktop
application/x-cd-image=gnome-disk-image-mounter.desktop
application/x-raw-disk-image=gnome-disk-image-writer.desktop
application/x-raw-disk-image-xz-compressed=gnome-disk-image-writer.desktop
x-content/software=nautilus-autorun-software.desktop
inode/directory=org.gnome.Nautilus.desktop
application/x-gnome-saved-search=org.gnome.Nautilus.desktop
x-content/audio-player=rhythmbox.desktop
x-content/audio-cdda=sound-juicer.desktop
application/mxf=org.gnome.Totem.desktop
application/ogg=org.gnome.Totem.desktop
application/ram=org.gnome.Totem.desktop
application/sdp=org.gnome.Totem.desktop
application/smil=org.gnome.Totem.desktop
application/smil+xml=org.gnome.Totem.desktop
application/vnd.ms-wpl=org.gnome.Totem.desktop
application/vnd.rn-realmedia=org.gnome.Totem.desktop
application/x-extension-m4a=org.gnome.Totem.desktop
application/x-extension-mp4=org.gnome.Totem.desktop
application/x-flac=org.gnome.Totem.desktop
application/x-flash-video=org.gnome.Totem.desktop
application/x-matroska=org.gnome.Totem.desktop
application/x-netshow-channel=org.gnome.Totem.desktop
application/x-ogg=org.gnome.Totem.desktop
application/x-quicktime-media-link=org.gnome.Totem.desktop
application/x-quicktimeplayer=org.gnome.Totem.desktop
application/x-shorten=org.gnome.Totem.desktop
application/x-smil=org.gnome.Totem.desktop
application/xspf+xml=org.gnome.Totem.desktop
audio/3gpp=org.gnome.Totem.desktop
audio/ac3=org.gnome.Totem.desktop
audio/AMR=org.gnome.Totem.desktop
audio/AMR-WB=org.gnome.Totem.desktop
audio/basic=org.gnome.Totem.desktop
audio/flac=org.gnome.Totem.desktop
audio/midi=org.gnome.Totem.desktop
audio/mp4=org.gnome.Totem.desktop
audio/mpeg=org.gnome.Totem.desktop
audio/mpegurl=org.gnome.Totem.desktop
audio/ogg=org.gnome.Totem.desktop
audio/prs.sid=org.gnome.Totem.desktop
audio/vnd.rn-realaudio=org.gnome.Totem.desktop
audio/x-ape=org.gnome.Totem.desktop
audio/x-flac=org.gnome.Totem.desktop
audio/x-gsm=org.gnome.Totem.desktop
audio/x-it=org.gnome.Totem.desktop
audio/x-m4a=org.gnome.Totem.desktop
audio/x-matroska=org.gnome.Totem.desktop
audio/x-mod=org.gnome.Totem.desktop
audio/x-mp3=org.gnome.Totem.desktop
audio/x-mpeg=org.gnome.Totem.desktop
audio/x-mpegurl=org.gnome.Totem.desktop
audio/x-ms-asf=org.gnome.Totem.desktop
audio/x-ms-asx=org.gnome.Totem.desktop
audio/x-ms-wax=org.gnome.Totem.desktop
audio/x-ms-wma=org.gnome.Totem.desktop
audio/x-musepack=org.gnome.Totem.desktop
audio/x-pn-aiff=org.gnome.Totem.desktop
audio/x-pn-au=org.gnome.Totem.desktop
audio/x-pn-realaudio=org.gnome.Totem.desktop
audio/x-pn-realaudio-plugin=org.gnome.Totem.desktop
audio/x-pn-wav=org.gnome.Totem.desktop
audio/x-pn-windows-acm=org.gnome.Totem.desktop
audio/x-realaudio=org.gnome.Totem.desktop
audio/x-real-audio=org.gnome.Totem.desktop
audio/x-sbc=org.gnome.Totem.desktop
audio/x-scpls=org.gnome.Totem.desktop
audio/x-speex=org.gnome.Totem.desktop
audio/x-tta=org.gnome.Totem.desktop
audio/x-vorbis=org.gnome.Totem.desktop
audio/x-vorbis+ogg=org.gnome.Totem.desktop
audio/x-wav=org.gnome.Totem.desktop
audio/x-wavpack=org.gnome.Totem.desktop
audio/x-xm=org.gnome.Totem.desktop
image/vnd.rn-realpix=org.gnome.Totem.desktop
image/x-pict=org.gnome.Totem.desktop
misc/ultravox=org.gnome.Totem.desktop
text/google-video-pointer=org.gnome.Totem.desktop
text/x-google-video-pointer=org.gnome.Totem.desktop
video/3gpp=org.gnome.Totem.desktop
video/dv=org.gnome.Totem.desktop
video/fli=org.gnome.Totem.desktop
video/flv=org.gnome.Totem.desktop
video/mp2t=org.gnome.Totem.desktop
video/mp4=org.gnome.Totem.desktop
video/mp4v-es=org.gnome.Totem.desktop
video/mpeg=org.gnome.Totem.desktop
video/msvideo=org.gnome.Totem.desktop
video/ogg=org.gnome.Totem.desktop
video/quicktime=org.gnome.Totem.desktop
video/vivo=org.gnome.Totem.desktop
video/vnd.divx=org.gnome.Totem.desktop
video/vnd.rn-realvideo=org.gnome.Totem.desktop
video/vnd.vivo=org.gnome.Totem.desktop
video/webm=org.gnome.Totem.desktop
video/x-anim=org.gnome.Totem.desktop
video/x-avi=org.gnome.Totem.desktop
video/x-flc=org.gnome.Totem.desktop
video/x-fli=org.gnome.Totem.desktop
video/x-flic=org.gnome.Totem.desktop
video/x-flv=org.gnome.Totem.desktop
video/x-m4v=org.gnome.Totem.desktop
video/x-matroska=org.gnome.Totem.desktop
video/x-mpeg=org.gnome.Totem.desktop
video/x-ms-asf=org.gnome.Totem.desktop
video/x-ms-asx=org.gnome.Totem.desktop
video/x-msvideo=org.gnome.Totem.desktop
video/x-ms-wm=org.gnome.Totem.desktop
video/x-ms-wmv=org.gnome.Totem.desktop
video/x-ms-wmx=org.gnome.Totem.desktop
video/x-ms-wvx=org.gnome.Totem.desktop
video/x-nsv=org.gnome.Totem.desktop
video/x-ogm+ogg=org.gnome.Totem.desktop
video/x-theora+ogg=org.gnome.Totem.desktop
video/x-totem-stream=org.gnome.Totem.desktop
x-content/video-dvd=org.gnome.Totem.desktop
x-content/video-vcd=org.gnome.Totem.desktop
x-content/video-svcd=org.gnome.Totem.desktop
x-scheme-handler/pnm=org.gnome.Totem.desktop
x-scheme-handler/mms=org.gnome.Totem.desktop
x-scheme-handler/net=org.gnome.Totem.desktop
x-scheme-handler/rtp=org.gnome.Totem.desktop
x-scheme-handler/rtsp=org.gnome.Totem.desktop
x-scheme-handler/mmsh=org.gnome.Totem.desktop
x-scheme-handler/uvox=org.gnome.Totem.desktop
x-scheme-handler/icy=org.gnome.Totem.desktop
x-scheme-handler/icyx=org.gnome.Totem.desktop
x-scheme-handler/ghelp=yelp.desktop
x-scheme-handler/help=yelp.desktop
x-scheme-handler/info=yelp.desktop
x-scheme-handler/man=yelp.desktop
```