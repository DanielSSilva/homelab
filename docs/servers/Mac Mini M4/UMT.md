> UTM employs Apple's Hypervisor virtualization framework to run ARM64 operating systems on Apple Silicon at near native speeds.

Since I'm running [Home Assistant](../../services/Home%20Assistant.md)  on this mac, I needed a way to run it in a VM. I've decided to try UTM, as it seems to be optimized especially for the M series macs.

However, the biggest challenge is that there's in-app way to start the VM on boot. Instead, I have to use Automator to do the following:
    - Launch the UTM app
    - Wait 60 seconds to ensure that the app has started
    - Run command that calls UTM's command line tool to start the VM
    - Wait 30 seconds to ensure that the VM has started
    - Run a command that calls UTM's command line tool attach the USB device to the VM
    
![](../../Pasted%20image%2020250415174156.png)

!!! Tip 

    you can run `/Applications/UTM.app/Contents/MacOS/utmctl usb list` to list the USB Devices 


If you want a more detailed explanation why I'm running Home Assistant on this Mac, you can check out the [Home Assistant installation](../../services/home-assistant/Installation.md) page.
