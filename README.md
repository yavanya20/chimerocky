 # chimerocky (or just bedrock on top of chimera with sway)

A Chimera guide, with lightweight Sway and bedrock, as a main branch for installing apps from another "realms". "


# What "Chimerocky" really is?

How explained right on top, just a guide for making your chimera easy to install another apps, and be very, very lightweight. Altthought, its not install script or iso (that would be easier), just a guide. Screenshot it, copy/paste on usb with chimera, whatever.


# Guide. Chapter one: Chimera Installation.

Here i will provide the full guide for Chimerocky (Chimera + bedrock + sway, that we will install in process).

So firstly, all you want to do, is obviously install chimera iso. https://chimera-linux.org/downloads/ is the official site for downloading the images. Then, use the documentation on installing the chimera linux (its kinda like arch, you need to do it manualy). Then, after succesfully installing the system and rebooting (follow [docs](https://chimera-linux.org/docs/) to install it, or use installation script), make sure everything works just fine. Be aware, that some apps or things couldn't be installed of dinit/musl on chimera, as it standarts of chimera linux. Also i really recommend to install base apps, like dolphin or nautils, vim, emacs or nano, git and other very important things.


# Guide. Chatper two: Bedrock Installation.

You installed the chimera? Nice! We can move on installing bedrock. ( ITS OPTIONAL!!! BE AWARE, THAT BEDROCK IS QUITE UNSTABLE, WHEN SYSTEMS LIKE DEBIAN UPDATING THEIR PACKAGE MANAGER!!! But if you choose to not install the bedrock, move on Sway installing.) So everything you gotta do, firstly look at the [Bedrock Compability](https://bedrocklinux.org/0.7/distro-compatibility.html). Look at the Alpine compability (or other ones, if you want to install bedrock on other OSes, but we talking about bedrock on Chimera, so i wont provide any other guide on other distros). If you still want to do it, look at the [installation instruction](https://bedrocklinux.org/0.7/installation-instructions.html). And in the end you will see the scirpt to actually install the bedrock, but firstly install the sh script, you can find these in [here](https://raw.githubusercontent.com/bedrocklinux/bedrocklinux-userland/0.7/releases), and then run the sh script ( sh ./the-sh-script-you-downloaded.sh --hijack ). (run it as a root user, using doas) and then reboot. Also, in the bottom of the installation instruction. there is command "brl tutorial basics", that you should run after the installation for an interactive tutorial covering Bedrock's basic usage. Every other info you can find in their [official site](https://bedrocklinux.org/). 


# Guide. Chapter 3: Sway installation.

Finally we getting into Sway installation. Instead of Bedrock and Chimera installation, its actually pretty hard. Actually, you can choose between i3 and sway, because they are both same, but sway is on wayland, as wayland is much better than X11. Then, run the following command:
"doas apk add sway foot fuzzel swaybg swaylock swayidle i3status-rust" (you can replace foor with any wayland terminal, in this guide it uses foot because of lightweight).
Because Chimera uses dinit and relies on turnstile / seatd for managing user sessions and hardware access (like your graphics card and input devices), you need to make sure your user is in the correct groups and the services are running.
(doas adduser your_username video && doas adduser your_username input)
and also 
(doas dinitctl enable seatd && doas dinitctl start seatd)
Make sure you have the correct Mesa/graphic drivers installed for your hardware.
Intel: doas apk add mesa-dri-intel 
AMD: doas apk add mesa-dri-radeon
NVIDIA: If you are running Nvidia, note that Sway requires the backend openheads or specific environment variables (--unsupported-gpu), and you will need the proprietary drivers or Nouveau firmware setup.
Chimera comes with PipeWire, but you should ensure the user services for audio are active so your volume keys and status bar work correctly. Turnstile should handle user-level dinit services automatically when you log in.
To check or enable PipeWire for your user session:
dinitctl --user enable pipewire
dinitctl --user enable wireplumber
Since Sway is a Wayland compositor, it should be launched directly from the TTY (text console) rather than using startx.
Log out of your current session or reboot. At the TTY login prompt, enter your username and password. Start Sway by typing:
sway


# Guide. Chapter 4: Sway config

THIS IS VERY HARD PART COMES IN because it only base on what you like or love. You can only make sway by yourself in config, so you SHOULD chat with ai to help you with making your own config. Unfortunately, i can't provide ANY type of help. Just search for configs, make it yourself, or use Ai to make it.


# What we will have after this?

Absolutely lightweight system. No glibs, no GNU, no systemd or OpenRC (and yes, no Openrc, when it is a good systemdSHIT replacement, still sucks in performance). The reason why i choosed sway, because its literally an i3 with wayland. 

# Update (27.05.2026)

There will be no releases for iso. Bedrock already makes your system "bedrocky", so every issue or request, that named "where is the release" will be closed.
