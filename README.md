# pomodoro-timer02

# Build Steps
Install Dependencies

npm install
Build for Linux

npm run build:linux
Build for Windows

npm run build:win
Build for all platforms

npm run build
Notes
Icons for Linux

The resolution of pomodorotimer03.png should be 512x512 or larger, square.

Dependency Versions

# The electron and electron-builder versions should be kept appropriate. The current settings (^33.0.2) are fine.

Permissions

AppImage files generated for Linux should have execute permissions.

chmod +x dist/*.AppImage
Icons on Windows

It is recommended that the resolution of the .ico file includes multiple sizes (16x16, 32x32, 48x48, 256x256, etc.).

Conclusion
This modified package.json conforms to the recommended settings and works for both Linux and Windows. Also, you can use the original pomodorotimer03.png as an icon without any problems.

3. Find an alternative to timespan

Since timespan is a deprecated package, consider using alternative packages such as the following:

moment: A well-known package that can be used when you need time management.
date-fns: A lightweight date manipulation library.
Install the alternative package and remove timespan from your project.

Example: Install moment

bash
Copy code
npm install moment
Remove timespan:

bash
Copy code
npm uninstall timespan

This error occurs because a specific GLIBC version required by fpm (Effing Package Management) is not installed. Specifically, it indicates that libcrypt.so.1 requires the GLIBC_2.2.5 version, but that version does not appear to be present on your current system.

You can try to resolve it with the following steps:

1. Install a compatible version of libcrypt
You can provide the required version of libcrypt by installing the libxcrypt-compat package.

bash
sudo dnf install libxcrypt-compat
2. Remove electron-builder cache
The electron-builder cache may be causing the issue. Remove the cache with the following command and try building again.

bash
rm -rf ~/.cache/electron-builder
3. Reinstall fpm
Reinstall fpm to ensure that required dependencies are set correctly.

bash
gem install --user-install fpm
Solution steps
Try these steps and see if they resolve your libcrypt-related issues.

Install libxcrypt-compat package

Remove electron-builder cache

Reinstall fpm

Try again. If this doesn't resolve your issue, let me know as there may be other things to check. I'll help!

nano ~/.local/share/applications/pomodoro-timer.desktop

[Desktop Entry]
Name=Pomodoro Timer
Comment=Pomodoro Timer Application
Exec=/home/hiroppy123/pomodoro-timer02/dist/Pomodoro-Timer-1.0.0.AppImage
Type=Application
Terminal=false
Icon=/home/hiroppy123/pomodoro-timer02/pomodorotimer03.png
Categories=Utility;

hiroppy123@fedora:~$ update-desktop-database ~/.local/share/applications

Click the icon to start
