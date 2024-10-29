## Complete Windows Optimization Guide
Windows, by itself, isn't a particularly optimized operating system. With its multitude of features, many of which are designed to generate revenue, it's difficult to achieve optimal performance straight out of the box. In contrast to Linux, which prioritizes overall performance and efficiency, we'll need to make some modifications to Windows to fully harness the potential of our machines.

*Oh and yeah..... if you can, consider switching to linux :)*

<br/><br/>

### Picking Up The Right ISO
Now, while not necessary this guide will be starting from reinstalling Windows 11. The first step is to pick the right ISO. Now some people will tell you that you should use a pre-modified ISO: which are just Windows 11 ISO's but modified by others to remove the bloatware and useless things. 

I wouldn't recommend something like this, since it's really hard to tell whether an ISO is secure or not for the most. So, my recommendation: Get the Official Microsoft Windows 11 ISO. We'll just make the changes after installing Windows itself.

So, head over to: https://www.microsoft.com/en-us/software-download/windows11 to grab the latest Windows 11 ISO.

<br/><br/>

### Windows Installation
For installing Windows 11, You will need:
- Windows 11 ISO Image
- Rufus (for creating a bootable pen drive): https://rufus.ie/en/
- A Pen Drive with at least 8 GB Storage (16GB or more recommended)

Here's the step by step guide for Windows Installation:
1. First backup all your data in the computer, as even though it's possible to not delete any data while reinstalling Windows, it's better to clear everything and get a fresh start.


2. Open Rufus, and connect your pen drive to your system. You should be able to see the pen drive's name at the top of your Rufus Window. In the boot selection option, press select and choose the Windows 11 ISO downloaded from the official Microsoft Link. Press Start. When Prompted for Windows Customization, Choose the options:
    - (Optional) Remove requirements for 4GB+ RAM, Secure Boot and TPM 2.0
    - Remove Requirement for an online Microsoft Account
    - Create a local account with username: <any_username>
    - Disable data collection (skip privacy option)


3. After the setup is finished, boot into boot options, and select the pen drive to boot from. To find the boot options for your laptop/desktop, you can google the model, or use: https://techofide.com/blogs/boot-menu-option-keys-for-all-computers-and-laptops-updated-list-2021-techofide/ to find the key.

4. During Windows Installation, a few things must be considered:
    - Choose English World as time and currency. This will remove most of the bloatware.
    - If your installation media is missing during disk selection, you might need to manually install Intel Rapid Storage Technology Drivers (Intel RST). Download the drivers from [here](https://www.mediafire.com/file/l2di0f6wpn77ghv/Intel_RST_VMD_Controller_9A0B.zip/file), and extract them to the installation pen drive. When prompted, choose load manually and browse to the folder containing the driver. Choose any one from the list.
    - Delete all the partitions related to Windows. If you do not want to save ANY data (such as D: E:) you can delete all the present partitions before hitting next.

5. Once Your System wants to reboot after installation, remove the installation pen drive.

<br/><br/>

### Initial Windows Setup
During the Windows 11 Initial setup screen, if you chose your region as English World, it may give an error. You can safely skip this. Most of the things it will ask shouldn't be a bother. However if it does ask something, here's the tips:
- If it asks for data collection options, turn them all off.
- If it asks for Microsoft Account Login, either skip it, or if the option is not given, press ```Shift + f10``` to launch CMD, then type the command ```oobe\bypassnro``` which will restart the computer. Another option if this gives an issue is to again, press ```Shift + f10``` and then in CMD type ```ipconfig /release``` then go back from the login screen, and you should have the option to setup a local account.

Once Windows Launches, make sure to set your region back to get a working Microsoft Store:
- Go to settings app
- On the left side go to the ```Time and Language``` section
- Go to the ```language and region``` Tab
- Update your ```Country or Region``` to the correct one
- Go back and then in the ```Date & Time``` Tab
- Select the timezone where you live

Once this is done, you should be able to use Microsoft Store as normal. 

Now you can:

<br/><br/>

### Update Windows
Firstly update your Windows System. This will get the latest drivers and system update. Windows should automatically take care of this, however to make sure,
- Open the settings app
- Head Over to the Windows Update tab on the left
- Press check for updates, or update all if present

<br/><br/>

### Update Nvidia Driver
If you have an Nvidia Graphics Card you need to make sure it's updated. There are two ways to update the driver for Nvidia Graphics Card:
1. First way is to update using Nvidia Control Panel:
    - Right Click on the windows desktop and select ```Nvidia Control Panel```
    - Navigate to the help menu and select updates

2. Second Method is to manually download the driver
    - First let's figure out the Graphics Card you have. If you already know it, skip this step. Press ```Windows Key + R``` to open run dialog, and type ```dxdiag``` and press ok. Once the window open, go the tabs on the top labelled ```display``` to check the one with Nvidia Graphics Card. Note down the name.  
    - Navigate to https://www.nvidia.com/en-us/drivers/ 
    - In the search field, search the name of your graphics card and open the relevant one.
    - Download the Latest Nvidia Game Ready Driver
    - Open the installer and follow the on screen prompts. DO NOT INSTALL Geforce Experience App unless you have a really good reason to. 

<br/><br/>

### Use Chris Titus Tech Tool
The YouTuber Chris Titus Tech has created a really great and simple to use app which allows to make automatic tweaks to Windows. To use the tool:
1. Search Powershell in start menu, right click and run as administrator
2. Type ```irm christitus.com/win | iex``` in the window and hit enter
3. Once the window launches, head over to the ```Tweaks``` tab up top, and from the ```Recommended Selections```, select the ```standard``` option
4. Press ```Run Tweaks``` at the bottom 
5. DO NOT USE THE ULTIMATE PERFORMANCE POWER PLAN. Unless you are running a really high end PC with AIO Coolers, it's probably gonna cause more issues than fix them. I'll talk in the next section about what's the best power options.
5. Once Finished, head over to the ```Updates``` tab at the top, and select the ```Security (Recommended) Settings```
6. Exit the program and powershell

<br/><br/>

### Change the power plan
Now, let's manually adjust the power plan to reduce the temperatures and improve performance.
1. Search for ```Edit Power Plan``` in the start menu and open it.
2. Make sure you are using the ```balanced power mode```. Ultimate or High Performance will lead to more issues
3. Press ```Change Advanced Power Settings``` and change the following settings:

    - Wireless Adapter Settings
        - Power Saving Mode
            - On Battery: Medium Power Settings
            - Plugged in: Maximum Performance
        
    - USB Settings
        - USB Selective Suspend Settings
            - On Battery: Disabled
            - Plugged in: Disabled

    - Intel ® Graphics Settings
        - Intel ® Graphics Power Plan
            - On Battery: Balanced
            - Plugged in: Maximum Performance
    
    - PCI Express
        - Link State Power Management
            - On Battery: Maximum Power Savings
            - Plugged in: Off

    - Processor Power Management
        - Minimum Processor State
            - On Battery: 5%
            - Plugged in: 5%
        
        - System Cooling Policy
            - On Battery: Active
            - Plugged in: Active
        
        - Maximum Processor State
            - On Battery: 100%
            - Plugged in: 100%

<br/><br/>

### Setup Auto Defragment For Your Hard Disk
SKIP THIS IF YOU ARE USING AN SSD. In a hard drive the data can become scattered to different places. Hence the disk head has to jump a lot more between places to get data which definitely slows it down. This will only help in case you are using a hard disk. To check if you are:
- Search for ```Defragment and Optimize Drives``` in the start menu
- In the listed drives, check the column named ```Media Type```. If it says ```Solid State Drive``` skip this section.

If the drive is a ```Hard Disk Drive```, then set up auto defragment as follows:
- In the ```Defragment``` Window, under the ```Scheduled Optimization``` press ```change settings```.
- In the new window, tick ```Run on a schedule``` with frequency ```Weekly```
- Leave the rest default and hit ok and close the defragment window.

<br/><br/>

### Remove the unnecessary apps
This step will allow you to reduce the number of background processes, and also free up extra space. To remove unwanted or unnecessary apps:
- Open the ```Settings``` app from start menu
- Go to ```Apps``` in the left tab
- Open the ```Installed Apps``` tab
- Go through the list and remove all the apps you don't use. If there are some which you are uncertain whether or not can be uninstalled, a simple google search should help. Search something like ```Is <app_name> safe to uninstall```

<br/><br/>

### Disable Unnecessary Startup Programs
Some apps start when Windows starts, effectively slowing down the boot time. You can disable these apps by:
- Press ```Ctrl + Shift + Esc``` or search for ```Task Manager``` in the start menu and open it
- In the Task Manager, go to the tab on the left which says ```Startup Apps```
- Disable any apps you don't want to start automatically by right clicking on the app name, and selecting disable.

<br/><br/>

### Use a custom DNS
A DNS is a service which converts the URL of websites (such as www.google.com) to it's IP Address (such as 142.251.xx.x). The default ISP DNS can be slow, and they can also track which sites you may be visiting. It's bette to use a custom DNS.

There are two DNS I recommend:
- Cloudflare (Loads websites faster): 1.1.1.1 & 1.0.0.1
- Adguard (Blocks ads on most sites and apps) : 94.140.14.14 & 94.140.15.15

To use one of these, or some other DNS you might have found online:
- Search ```Control Panel``` in the start menu
- In the windows, either select ```Network and Internet``` and then ```Network and Sharing Center``` or ```Network and Sharing Center``` if present directly.
- In the left panel, select ```Change Adapter Settings```
- Choose the Wi-Fi Network to which you are connected. Right click on it and choose ```Properties```
- In the list double click the option labelled ```Internet Protocol Version 4 (TCP/IPv4)```
- In the bottom section, choose the option ```Use the following DNS Server Addresses:```
- In the preferred address write the main DNS Address (for cloudflare it's 1.1.1.1)
- In the alternate address write the secondary DNS Address (for cloudflare it's 1.0.0.1)
- Hit ok and exit.

<br/><br/>

### (Optional) Disable/Reduce Turbo Boost
If you are on a computer without a good cooling system, such as a laptop, it tends to be better to disable turbo boost. Turbo boost is the technology which boosts the CPU to higher frequencies, however it also generates more heat. Reducing Turbo Boost should keep the heat to minimum, allowing for better performance. There shouldn't be any performance drop, though your experience may vary so make sure to test it well.

To Disable/Reduce Turbo Boost:
- Press ```Windows Key + R``` to launch the run window
- Type ```regedit.exe``` in the field and press ok
- In the registry editor window, in the address at the top where it probably says ```Computer``` or ```HKEY....``` write the following: ```HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\54533251-82be-4824-96c1-47b60b740d00\be337238-0d82-4146-a960-4f3749d470c7```
- On the right panel, double click on the file called ```Attributes``` and modify the value from ```1``` to ```2```. The data should read ```0x00000002 (2)```
- Search for ```Edit Power Plan``` in the start menu and open it.
- Press ```Change Advanced Power Settings```
- Adjust the settings:
    - Processor Power Management
        - Processor Performance Boost Mode
            - On Battery: Disabled
            - Plugged in: Disabled / Efficient Aggressive (Test which works best for you)

<br/><br/>

### (Optional) Use ISLC for low end PC
The Intelligent Standby List Cleaner is an utility which frees up memory taken by programs running in tha background. If you have a good amount of memory (RAM) then usage of this tool is discouraged. However if you have limited memory, here's the step by step guide:
- Download ISLC tool from https://www.wagnardsoft.com/forums/viewtopic.php?t=1256
- Open and Extract the files anywhere (it will permanently stay there so choose a permanent location for the tool)
- Run ```Intelligent Standby List Cleaner ISLC``` as administrator
- Tick the ```Start ISLC minimized and auto Start monitoring``` and ```Launch ISLC on user logon. (Task Scheduler)``` option. This will automatically run the app on each boot.
- Check ```enable custom timer resolution```
- Adjust the value of ```Wanted Timer Resolution``` to ```0.5000```
- Press the start button and minimize the software


### (Risky) Undervolting
Undervolting is an entire process. Here's the basics - The more power something uses, the more heat it generates - The more heat in the system, the slower it has to run to combat the heat - called as ```Thermal Throttling```.

In essence, while you may think using more power helps your system run faster, unless it can be properly cooled down, it actually slows down the pc to keep the CPU from frying itself.

This is where undervolting comes in. Undervolting is the process of limiting, or more accurately, offsetting the voltage you supply to your processor or the GPU, to allow it to run cooler, and get more performance per watt out of your machine without it thermal throttling

Since this is a lot risky, I will soon be creating a seperate guide on undervolting your GPU and CPU individually so you don't end up with a non-functioning device.


### Conclusion
These steps all should allow your pc to run better, using less power, yet giving more performance. I will be creating separate guides on CPU and GPU Undervolting. And I will also try my best to keep this guide updated. However these modifications may end up messing with your system, so try them out at your own risk.

Thanks for reading.
