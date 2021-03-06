# DualSense LED Configurator
![DS LED Config Screenshot](https://i.imgur.com/sVz4LCD.png)
This program allows the user to adjust color and brightness to the various LEDs found throughout the DualSense (DS). Rainbow, disco, or otherwise random effects can be applied, though these are unstable. Also fetches battery percentage and displays this.

## Prerequisites (besides your DS, obviously)
* Linux-based operating system
* Sony's official driver for the DualSense, available in the [AUR](https://aur.archlinux.org/packages/hid-playstation-dkms). As it's not in the kernel yet, you'll need to otherwise download the [patches](https://patchwork.kernel.org/project/linux-input/list/?series=404369) and compile the kernel
* Access to root privileges (the program modifies the values found in `sys/class/leds/playstation::[mac_address]::[name_of_LED]/`)
* Python 3
* GTK 3
* Tkinter

## What You Should Know
The program is highly unstable depending on what button you press, in particular:
* Rainbow LED colors
* Disco/Progress bar LED patterns

Pressing any of those types of buttons (which have been labeled as unstable accordingly) will cause the program to loop indefinitely. You'll need to one of the following:
* Press `Enter` in the terminal window to either close the application or keep it from looping
* force exit the application through your system monitor 
* disconnect your DS

Other tasks going on on your computer will still run regardless.

## How To Use
1. Clone the repository, i.e. `git clone https://github.com/cow-killer/dualsense-led-configurator.git`
2. Plug your DS in or connect it via Bluetooth, then take note of its MAC address (can be found in `sys/class/leds/`)
3. Open `ds_led.py` with a text editor, and fill in the MAC address at or somewhere near line 16
4. Save the file, then run the script as root: `sudo python ds_led.py`

## To-Do
* ~~Code is a mess, more than likely a way to reduce the amount of code needed~~ Thanks thats-the-joke!
* Much-needed UI polish
* Find a way to get rainbow LEDs, disco, etc. to work without hanging the application 
**Update 2/13/2021:** only Rainbow needs to get fixed now
* ~~Add a color picker~~
* Add a way to extract MAC address without user interaction
* Update UI if controller is plugged/unplugged and if the percentage of the battery has changed

Pull requests welcomed!
