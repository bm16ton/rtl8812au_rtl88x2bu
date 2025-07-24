
These are drivers for rtl8812au (supports rtl8812au and rtl8821au) and rtl88x2bu chipsets.

Things have changed in terms of setting/exporting/passing config options, You will need to edit the ccflags-y variable at bottom of the Makefiles to make any config changes, ill get around to making it work easier better someday.

Monitor mode on both drivers appears to work but I did very little testing.

Turns out the wireless freqs etc are not locked in by firmware so the rtl8812au driver has extra 2.4ghz channels (up to the 20's) tho without editing userland utils you probly wont see them or know they exist

AP mode is currently untested tho with earlier version of this driver (meaning before a lot of my edits to use on newer kernels) rtl8812au did work even on the extra channels.

The rtl8812au should have all wireless channel restrictions removed (be carefull! could be iliegal in your country, be smart) the rtl88x2bu I made changes, the driver reports all channels go, but that means nothing needs testing.

the rtll8812au originally came from the aircrack repo many moons ago, the rtl88x2bu came from

 [remote "origin"]
	url = https://github.com/cilynx/rtl88x2bu.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "5.8.7.1_35809.20191129_COEX20191120-7777"]
	remote = origin
	merge = refs/heads/5.8.7.1_35809.20191129_COEX20191120-7777


