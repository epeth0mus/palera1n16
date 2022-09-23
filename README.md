# palera1n
iOS 16.0-16.0.2 work in progress semi-tethered checkm8 "jailbreak"

# What does this do?
It boots the device with AMFI patches. Eventually, I want it to automatically install Pogo by Amy. For now, it has to be installed with TrollStore. You can get an IPA [here](https://nightly.link/elihwyma/Pogo/workflows/build/main/Pogo.zip). There is **no tweak injection yet**.

**NOTE**: `sudo usbmuxd -p -f` should fix most USB issues on Linux.

**NOTE 2**: Onboard blobs are pretty much needed so you don't get the black screen issue. Dump onboards with [SSHRD_Script](https://github.com/verygenericname/SSHRD_Script), then use that blob to boot with palera1n. Progress is being made for this to be done for you, check out the [ramdisk branch](https://github.com/itsnebulalol/palera1n/tree/ramdisk) if interested (it's currently not working).

**WARNING**: As of now, this is pretty unstable (atleast just on A11). On my A11 device, it has the deep sleep bug while booted with palera1n, and will kernel panic, or just not wake up until force rebooted, about a minute after being in sleep mode. Patching AMFI also seems to log you out of iCloud?

**WARNING 2**: I am NOT responsible for any data loss. While nothing should happen, jailbreaking has risks in itself. If your device is stuck in recovery, please run `futurerestore --exit-recovery`, or use irecovery.

**Known working devices:**
- iPhone X (GSM)
- iPhone 7 
- iPhone 6s (Only for the iOS 15.4 version of Palera1n)

# How to use
1. Install libimobiledevice
    - It's needed for `ideviceenterrecovery` and `ideviceinfo`
2. Clone this repo with `git clone https://github.com/itsnebulalol/palera1n && cd palera1n`
3. Prepare your onboard blob for the **current version** you're on
<!-- 4. Run `./palera1n.sh path/to/blob.shsh2 install`
    - \[A10+\] Before running, you **must** disable your passcode
    - If you want to start from DFU, run `./palera1n.sh path/to/blob.shsh2 --dfu <your iOS version here> install` -->
4. Run `./palera1n.sh path/to/blob.shsh2`
    - \[A10+\] Before running, you **must** disable your passcode
    - If you want to start from DFU, run `./palera1n.sh path/to/blob.shsh2 --dfu <your iOS version here>`
5. Make sure your device is in normal mode, if you didn't start from DFU
6. Follow the steps
    - Right now, getting into DFU is steps for A11, please suppliment the steps for your device
<!-- 7. Once your device reboots, run the script again, but without `install` -->
7. Install Pogo through TrollStore, then hit Install in the Pogo app!
    - You can get a Pogo IPA from [here](https://nightly.link/elihwyma/Pogo/workflows/build/main/Pogo.zip)
    - You should now see Sileo on your homescreen, enjoy!
    - You'll have to uicache in the Pogo app every reboot
8. Visit [ios 16 jailbreak](https://taig9.com/jailbreak/ios-16) for more jailbreak related details

# Credits
- [Nathan](https://github.com/verygenericname) for a lot of the code from SSHRD_Script
- [Mineek](https://github.com/mineek) for some of the patching and booting commands
- [Amy](https://github.com/elihwyma) for the Pogo app
- [nyuszika7h](https://github.com/nyuszika7h) for the script to get into DFU
- [the Procursus Team](https://github.com/ProcursusTeam) for the amazing bootstrap
- [Taig Jailbreak Team](https://taig9.com) for offcial news and blogging
