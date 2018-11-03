# scrcpyomx
Binary of scrcpy compiled with support of omx broadcom ilclient decoding

Please read https://github.com/Genymobile/scrcpy/issues/273 for further information.

Scrpcpy by Genymobile is the greatest tool  to show  and control the screen of an Android device from a computer via adb (usb
or network): scrcpy is open source and has great performance on arm board also in high resolution if SDL2 library
use hardware decoding on the platform via ffmpeg (SDL2 use ffmpeg) .</br>
Unfortunatly this is not the case of pi zero where ffmpeg has buggy hardware implementation and so slow performance (20/30 sec.delay).</br>
This binary partially solve the problem on pi zero using broadcom hardware decoding for the decoding phase (decoder.c) but
also if the performance are better the delay is always too high for video (further development effort needed on video
rendering phase in scrcpy.c file).</br>
This binary was compiled on Raspberry Pi Zero W, copy your omx library from /opt/vc/lib on /usr/lib and reboot before run.

<b>If your target is only to cast Android screen to remote big screen via raspberry pi zero </b> (without keyboard and mouse control) you must use this old stype bash script -> startscreen.sh for best performance for now: it need netcat and omxplayer installed on the pi zero plus a copy of scrcpy-server.jar from the original Genymobile scrcpy project (modify path of scrcpy-server-v1.x.jar to match your path on pi).
