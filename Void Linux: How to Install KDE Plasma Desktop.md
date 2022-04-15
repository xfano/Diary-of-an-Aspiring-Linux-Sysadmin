There's no official KDE ISO available for [Void Linux](https://voidlinux.org/download/); however, [Void Builds](https://www.voidbuilds.xyz/) created an [unofficial version](https://voidbuilds.xyz/download/).

But if you've already installed Void Linux and prefer installing KDE Plasma Desktop from there on, here's what you can do:

**1. Update the package manager XBPS:**

`sudo xbps-install -u xbps`

**2. Sync and update the XBPS repository:**

`sudo xbps-install -Su` 

**3. Install KDE Plasma Desktop, its base applications, and Xorg:**

`sudo xbps-install kde5 kde5-baseapps xorg`

**4. Enable KDE Plasma:**

`sudo ln -s /etc/sv/sddm /var/service`

**5. Reconfigure KDE Plasma:**

`sudo xbps-reconfigure -f plasma-workspace`

**6. Reboot Void Linux:**

`sudo reboot`

**NOTE:** After rebooting, I was able to choose KDE Plasma. But I had only been met with a black screen and a cursor. So I had to reboot again; maybe because I wasn't able to reconfigure it, which is step 5. 

After the second reboot and logging into KDE Plasma, I was met with a wallpaper and a cursor. I figured I had to make the panel and the widgets, which is not a problem at all. Then I did Step 5.

**TIP:** If there's still a problem running KDE Plasma, you might want to **disable elogind**.
