Lyrion Music Server (LMS) is a web service for manage squeeze kind of devices or players. It has no music player capability on it own. If you install from Ubuntu Server you need to do some work!
# Installation

## LMS
[Getting Started with LMS - Lyrion Music Server](https://lyrion.org/getting-started/)

```sh
wget <package from link above>
sudo dpkg -i <package>
```

create directories for music and playlist

```
sudo mkdir -p /home/squeeze/music
sudo mkdir -p /home/squeeze/playlist
sudo chown squeezeboxserver -R /home/squeeze/
```

## Install ALSA
You can also install `PulseAudio` if you want.

Add audio to root
```sh
sudo usermod -aG audio root
```

###  Testing ALSA

Test that `ALSA` is working with some player like `moc`

```sh
sudo apt install moc
mocp  # open moc
```

* Don't for get to add `audio` to your user before start `mocp`

Or just use `alsabat-test`

```sh
alsabat-test  # you may need to install alsa-utils
```

Open ALSA mixer if no sound

```sh
alsamixer
```

- Make sure **Master**, **PCM**, and **Speaker** aren't muted (`MM` = muted, `OO` = OK)
- Hit `M` to unmute

press F6 select a soundcard, then save by run

```
sudo alsactl store
```


# Install Squeezelite

`Squeezelite` is a small, lightweight, headless Squeezebox emulator that allows you to stream music from LMS.

There are multiple version of `Squeezelite` install it depend on your sound driver.
```
squeezelite/noble,now 1.9.9-1449+git20230814.8581aba-1build3 amd64 [installed]
  lightweight headless Squeezebox emulator - ALSA version

squeezelite-pa/noble 1.9.9-1449+git20230814.8581aba-1build3 amd64
  lightweight headless Squeezebox emulator - PortAudio version

squeezelite-pulseaudio/noble 1.9.9-1449+git20230814.8581aba-1build3 amd64
  lightweight headless Squeezebox emulator - PulseAudio version
```

```sh
# for ALSA
sudo apt install squeezelite
```

Test that the `squeezelite` can see audio output

```sh
$ sudo squeezelite -l
Output devices:
  null                           - Discard all samples (playback) or generate zero samples (capture)
  default                        - Default Audio Device
  sysdefault                     - Default Audio Device
  iec958                         - IEC958 (S/PDIF) Digital Audio Output
  hw:CARD=AudioPCI,DEV=0         - Ensoniq AudioPCI, ES1371 DAC2/ADC - Direct hardware device without any conversions
  hw:CARD=AudioPCI,DEV=1         - Ensoniq AudioPCI, ES1371 DAC1 - Direct hardware device without any conversions
...
```
