# Firefox on Haiku R1/beta5

This is a practical note from ![KENZ](https://discuss.haiku-os.org/u/KENZ)'s https://discuss.haiku-os.org/t/progress-on-porting-firefox/ original post and discussions. Content of this repo is only for testing and experimental purposes only. Feel free to join in on the development, play around, and even consider sponsoring!

Thanks to everyone who contributed on this! 🤗

All content and files are up to date as of 25/10/2024. 

<br><br>

**Step 1: Install dependencies**

1. Download files

Goto https://discuss.haiku-os.org/t/progress-on-porting-firefox/13493/206 to get the two files: a .tar.bz2 and a .hpkg file.

2. Run a full upgrade in Haiku Depot.

3. Install the following packages using pkgman:
```bash
pkgman install atk dbus dbus_glib ffmpeg gettext_libintl glib2 graphite2 harfbuzz libnotify libpng16 pango pciutils libevent
```
If you encounter errors, you can check the syslog to determine which library is missing by running `cat /var/log/syslog`.

3. Install the attached `.hpkg` file. You may need to uninstall the pre-installed version that comes with Haiku R1/beta5. Simply double-click on the `.hpkg` file and click the "Uninstall" button in the Depot GUI.

**Important:** Be sure to check which packages were automatically removed by pkgman during this process and reinstall them manually.

<br><br>

**Step 2: Extract the Firefox compressed file .tar.bz2**

<br><br>

**Step 3: Launch Firefox**

Run the following command: （or just simply `firefox`）

```bash
export WAYLAND_DISPLAY=:0

firefox --no-remote --safe-mode --disable-gpu --disable-extensions --disable-smooth-scrolling --disable-restore-session-state --disk-cache-size=1048576 --disable-http-cache --disable-crash-reporter --disable-autofill-keyboard-accessory-view
```

<br><br>

**Additional useful information**

To make video work:

https://github.com/kenz-gelsoft/gecko-dev/issues/58

<br><br>

![Image](https://github.com/user-attachments/assets/6dc8f209-df0a-4d55-99c2-aed7a9029880)
