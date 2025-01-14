---
title: 2021-2022 Roadmap
permalink: contribute/roadmap.html
summary: As 2022 nears, we'd like to share our plans going forward.
---
## dahliaOS: 2021-2022 Roadmap

You may have noticed that it has been over a year since the last release of dahliaOS. A year-and-a-half ago, we released dahliaOS version 200614, the first release to feature the Pangolin desktop. 6 months and 4 incremental updates later, we released dahliaOS version 201215. As 2022 nears, we'd like to share our plans going forward.

### dahliaOS Linux 22*

Over the course of last year, we've made numerous improvements to our desktop and software, which will be available at or before Q1 2022

#### Desktop Changes

We spent 2021 rebuilding Pangolin from the ground up. Here's what's new:

* Desktop Redesign: Pangolin has been completely rebuilt, with new features and functionality
  * New Search Functionality: You can now search through apps quickly, speeding up multitasking.
  * Improved Launcher: The launcher has been redesigned to separate applications into different categories
			* Improved Quick Settings Menu: The Quick Settings menu has redesigned to prioritize the viewing of relevant information and configuration options.
			* Improved Taskbar: Applications can be pinned and unpinned, and windows can be minimized en-masse using the Show Desktop button.
* New Window Manager: A new window manager for Pangolin, Utopia, improves the handling of windows and fixes memory issues caused by the previous window management solution.
* New Onboarding Interface: The new onboarding interface enables faster testing, configuration. The legacy command-line interface is still available for those with advanced needs.
* Improved Applications: Files, Settings, Terminal, and Task Manager have received significant updates to functionality and visuals.

#### Underlying software 
		
2021 was a significant year for the lower levels of the system as well, which will also be released at or before Q1 2022, packaged with the latest version of the Pangolin Desktop.
		
* All new cross-platform package management solution: The Dart-based Dap package manager, developed for dahliaOS, provides a simple, extensible way of managing packages
  * New software packaging method: With Dap, we've worked on the a preliminary standard for dahliaOS packages, .dap, that provides self-contained and secure applications built on the AppImage Type 2 specification, customized for dahliaOS.
  * Seamless software updates: Using Dap, core components of the system can be updated seamlessly in the background as soon as updates are available.
* Improved drivers: We've updated the graphics drivers to ensure the best possible desktop performance, even on older devices.
* New filesystem support: We've moved the system over to BTRFS to provide snapshotting and faster disk I/O performance.


### Improvements to the Release Schedule

In 2021, we did not release software as frequently as we would have liked to. Going forward, starting with dahliaOS Linux 22*, we are going to ensure timely and consistent updates to our software. Updates to dahliaOS Linux and FImage will be released monthly, with security and other required updates released as needed. 

### Our commitment to Fuchsia-based software

In 2022, we aim to begin the process of porting over our work to Zircon. Limited access to hardware has made this difficult in years prior, but we will be able to accelerate our workflow using FImage. Additionally, FImage will continue to be updated.

### More to come!

2021 was a very productive year, and 2022 will be even more so! Thank you for your support!
