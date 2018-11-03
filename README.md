# scrcpyomx
Binary of scrcpy compiled with support of omx broadcom ilclient decoding

Please read https://github.com/Genymobile/scrcpy/issues/273 for further information.

Scrpcpy is a great tool written by Genymobile to show  and control the screen of an Android device from a computer via adb (usb
or network), scrcpy is open source and has great performance also in high resolution screen if SDL2 library use native hardware
decoding via ffmpeg (SDL2 use ffmpeg).
Unfortunatly this is not the case of pi zero where ffmpeg has buggy hardware implementation and slow performance (20/30 sec.delay).
This binary scrcpyomx try to solve delay problem on pi zero using broadcom hardware decoding for the decoding phase (decoder.c) but
also if the performance are better the delay is always too high for video (2/5 sec), further development effort are on the video
rendering phase in scrcpy.c file.
Please give me a feedback if you are interested in scrcpy dev on pi zero.

If your target is only to cast Android screen to remote big screen via raspberry pi zero w  (without keyboard and mouse control)
you can use an old stype bash script like startscreen.sh: it need netcat and omxplayer installed on the pi plus a copy of 
scrcpy-server.jar android app from the original Genymobile scrcpy project (modify path of scrcpy-server-v1.x.jar to match your
path on pi).
