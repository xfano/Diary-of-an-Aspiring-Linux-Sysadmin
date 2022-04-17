Like you, I enjoy customizing my desktop (or ricing). I prefer **KDE Plasma Desktop Environment** because I don't have the time to learn Window Managers yet. When I thought was finished, I noticed that my desired cursor theme (DCT) is **_not applied globally_**; that when I hover on the desktop, the cursor _reverts_ to the default KDE Classic cursor theme.

Of course I searched up for answers online to such a frustrating situation. Many suggested that one has to edit the ``index.theme`` file in the ``default folder`` in ``/usr/share/icons`` directory to set the desired cursor theme globally. But in my case, **Void Linux** _doesn't seem to have that file_.

When I checked Icons directory, I realized that my DCT can't be set globally because _its folder and the default folder_ is just not there. I'm only a beginner. I don't know where to find its folder and I tried looking for it! I wanted to just copy and paste it in the Icons directory because maybe that's the solution.

So I decided to _download the tar of my DCT from the KDE store_ from my browser. 

---

Then I encountered another problem: I can't seem to find the tool to **extract tar.xz**. After some research, here's what worked: 

**1. Download xz:**

``sudo xbps-install xz``

**2. Extract your DCT from where it's been downloaded to:**

``cd Downloads``

``tar -xf cursor-theme-name.tar``

---

I was happy until I realized I simply can't copy and paste my DCT folder in the Icons directory. It seems to me that Void Linux doesn't have the ``use as root`` option for Dolphin. No matter, there's the commandline for that. But it _still didn't work_. 

I have made the ``default folder`` and the ``index.theme`` with the content: 

``[Icon Theme]`` <br/>
``Inherits=DCT``

Nope. 

**The problem remains: DCT reverting to KDE Classic on desktop.** 

So I thought I'd have to mess with the KDE Classic folder in the Icons directory.

---

**Note:** If you like the KDE Classic cursor theme, make a backup of its `cursor` folder; here's how:

``sudo cd /usr/share/icons/KDE_Classic``

``sudo cp -R cursor /desired/directory/``

---

**For the cursor theme problem,** here's what worked:

**1. Remove the cursors folder in KDE Classic directory**

``cd /usr/share/icons/KDE_Classic``

``sudo rm -r cursors``

**2. Go to the directory where your DCT is**

``cd /DCT/directory``

``cd DCT_folder``

**3. Copy your DCT's cursors folder to KDE Classic directory**

``sudo cp -R cursors /usr/share/icons/KDE_Classic``

**4. Go to the System Settings, then Appearance, and lastly, Cursors:**

Choose and apply KDE Classic that _should now reflect your DCT_. 

If not, you may need to reboot.
