# firmware-mod-kit

Based on the firmware-mod-kit by devttys0 (which also holds the binwalk code) and heffnercj.

Original repository: https://code.google.com/archive/p/firmware-mod-kit/  
Binwalk repository: https://github.com/devttys0/binwalk  

The code was old and the binwalk version wasn't compatible with new Python versions and architectures. This is a mixed version of both the codes. Tested with TP-Link MR3020 images.

## Usage ##

Due to the old script, this must be run as root, so I'll just assume that.

Go to firmware-mod-kit/src/binwalk and install it. Instructions are there, but basically run:

Python 2.7: python setup.py install  
Python 3.x: python3 setup.py install  

For further information refer to INSTALL.md in that directory.

After that, in firmware-mod-kit dir, just use extract-firmware.sh	and build-firmware.sh as the documentation. Without arguments they will show usage options, but the extractor receives the image and extracts to fmk dir, and builder but the new-firmware.bin file inside fmk dir.

Also, I find out safer to see the image being written from telnet. To that, use:

write /tmp/new-firmware.bin linux

System won't boot even in the case of success, so I recommend a boot after. It's very verbose so you should see the errors there (trx header appeared a lot to me before I put this together).
