On my [Framework](https://frame.work/) 12th gen Intel Laptop I was having an issue with screen freezes.

The cause seems to be the Intel 12th gen power saving features (panel self refresh) not working correctly on Linux yet. 

This might not be an issue in wayland, this fixes it in xorg: 

`sudo grubby --update-kernel=ALL --args="i915.enable_psr=0"`

Then reboot.

