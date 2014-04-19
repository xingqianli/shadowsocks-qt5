Shadowsocks-Qt5
===============

[中文用户指南](https://github.com/librehat/shadowsocks-qt5/wiki/%E7%94%A8%E6%88%B7%E6%8C%87%E5%8D%97)

Introduction
------------

Shadowsocks-Qt5 aims to be a fast and platform-cross GUI Client for [Shadowsocks](http://shadowsocks.org).

Latest Development Version: 0.3.0

Features
--------

Shadowsocks-Qt5 is written in pure C++ with Qt5 magic. It is not a standalone programme. But only works along with ss-local binary from [shadowsocks-libev project](https://github.com/madeye/shadowsocks-libev).

An intuitive and native UI. And JUST a **GUI**. Keep your favourite Shadowsocks port as backend.

The `gui-config.json` file is partially compatible with [shadowsocks-gui](https://github.com/shadowsocks/shadowsocks-gui). In order to serve better, some new values have been added.

`gui-config.json` is located under ~/.config/shadowsocks for UNIX users, or under the main programme's directory for Windows users.

Note
----

- Shadowsocks-Nodejs port is highly recommended to serve as backend for its better I/O performance.
- Don't be panic if you encounter a bug. Feel free to open [issues](https://github.com/librehat/shadowsocks-qt5/issues). Remember to run from terminal or `cmd` and paste the output.

ScreenShots
-----------

![image](https://github.com/librehat/shadowsocks-qt5/raw/master/screenshots/linux_main.jpeg)

![image](https://github.com/librehat/shadowsocks-qt5/raw/master/screenshots/linux_about.jpeg)

Installation
------------

### Windows ###

Downloading the prebuilt bundle (only **32-bit**) from [releases](https://github.com/librehat/shadowsocks-qt5/releases) is recommended because the bundles include `ss-local.exe`. For those who want to build from source, follow the instructions below.

Open this project using Qt Creator and build it.

Or type the command in MSYS.

```bash
qmake INSTALL_PREFIX=../ss-qt5
make
make install
```

You will get `ss-qt5.exe` and `gui-config.json` in ../ss-qt5 directory.

### Linux ###

You should have installed Qt 5 and its development packages before building.

```bash
# Some distros use seperated qmake-qt4, qmake-qt5. Then, just run `qmake-qt5`. You can specify INSTALL_PREFIX=/usr/local if needed. default is /usr
qmake INSTALL_PREFIX=/usr
make
make install
```

Usage
-----

You may have to specify the `ss-local` or `sslocal` (depends on which port of Shadowsocks you use) if `ss-qt5` didn't find it.

For Shadowsocks-Nodejs port backend, the backend path need to be set to `sslocal` script or `sslocal.cmd`. In most cases, you don't have to worry about it, because it should have been automatically found in *PATH*.

Clicking minimise button would hide the main window. Close button is used to exit. Meanwhile, Systray icon is always visible.

All output of `ss-local` or `sslocal` can be viewed in **Log** tab.

Once you click the **Save** button, the configuration would be written into file. Before that, you can click **Reset** button to restore the previous values stored in `gui-config.json`.
