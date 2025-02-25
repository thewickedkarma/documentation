---
title: The Pangolin Desktop
permalink: pangolin/pangolin.html
summary: Development History, features, and functionality of the Pangolin Desktop
---
## Pangolin Desktop (Zircon & Linux)

Pangolin Desktop UI shell, designed for dahliaOS, written in Flutter.

As of v200614.1, Pangolin has been available by default as the desktop in Linux-based builds. 

Try out the builds [here](https://web.dahliaos.io).

### History / significant changes

+ February 27, 2019, Camden Bruce announced the beginning of dahliaOS ([Source: Reddit](https://www.reddit.com/r/Fuchsia/comments/av6tja/fuchsia_fork_dahlia_os/))
+ March 2, 2019, Camden Bruce created the repository pangolin-desktop 
+ March 4, 2019, Noah Cain uploaded the first basic code for the desktop in a (now deprecated) custom codebase. 
+ April 5, 2019, Horus125 Begain importing some components from capybara for use within Pangolin
+ May 11, 2019, A basic calculator application was added to the system
+ May 17, 2019, A Text editor called "Petal" was merged into Pangolin
+ June 30, 2019, The launcher was given an updated look featuring cards, was not yet functional
+ May 26, App icons were finally added to the launcher, they were not yet functional
+ May 31, 2020, [@kanouharu](https://github.com/kanouharu) implemented a basic app launching ability to the panel icons
+ June 6, 2020, a basic task manager was implemented
+ June 12, 2020, [@SincerelyFaust](https://github.com/SincerelyFaust) migrated the codebase to Apache 2.0 rather than the GPL, the beginning of dahliaOS' transistion to Apache.
+ June 20, 2020, [@larsb24](https://github.com/larsb24) made significant changes to the backend as well as improving the quicksettings. 
+ June 22, 2020, FleshRoots added support for automatic building

Please note that these are only the highlights from development, and not indicative of every commit. 

If you find something left out, please feel free to add it.

### Components


#### Desktop, panel and quick settings

<div align=center>
<img width="100%" src="../img/screenshot/22xxxx/settings.png"/>
</div>

Pangolin Desktop, settings and start menu.

Quick settings assists in changing relevant system settings quickly (hence the name), offering an easier and more efficient method of changing settings than opening the app.

#### Launcher

<div align=center>
<img width="100%" src="../img/screenshot/22xxxx/search.png"/>
</div>

Pangolin Desktop, Calculator, Terminal, Notes and search.

A search bar is also available to sort through apps, find settings, and search the web. 

### Development

#### TL;DR for Linux

```bash
flutter channel master # Set flutter to master channel
flutter upgrade # Upgrade to master channel
flutter config --enable-linux-desktop # Add Linux as a target
git clone https://github.com/dahliaos/pangolin-desktop pangolin_desktop # Clone the repo
cd pangolin_desktop
flutter create . # Optional, but updates the embedder code
flutter run -d linux
```

### Developing Pangolin for dahliaOS Linux-Based builds

While pre-compiled builds can be found in the dahliaOS-overlays folder, you can also compile Pangolin and include them in the Buildroot toolchain.

Pangolin can also be added as a dependency inside of Buildroot via the 'dahliaOS core applications' section under 'Target Packages'

### Prerequisites

To develop for dahliaOS Linux-Based builds, you will need the `flutter` tool, and a compiled base config from dahliaos/buildroot. 

Compiling the base config will take about 4 hours. 

Pangolin will automatically be installed using the x86_64 configuration, but arm64 builds will require a Raspberry Pi 4 with the Flutter tool installed to produce an arm64 Linux-compatible bundle.
