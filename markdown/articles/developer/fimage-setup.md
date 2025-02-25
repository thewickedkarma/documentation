---
title: Setting up FImage for Application Development
permalink: developer/fimage-setup.html
summary: Guide to setting up FImage for Flutter development
---
## Setting up FImage for Application Development
This guide will explain how to bring your existing Flutter application to Fuchsia using the Flutter SDK and FImage.

### Prerequisites
You'll need a few things before working with Flutter apps on Fuchsia.
* A working installation of the latest version of the [FImage tool](https://docs.dahliaos.io/os/fimage)
* The [Flutter SDK](https://flutter.dev/docs/get-started/install/linux)
* The `ssh-keygen` tool
### Step 1 - Configuring Flutter for Fuchsia
Begin by upgrading Flutter to the `master` channel.
```Bash
flutter channel master
```
Then, enable Fuchsia development, and upgrade the Flutter tool. It should download the Fuchsia SDK. If `flutter devices` does not list the `fuchsia_fimage` device, run this step again.
```bash
flutter config --enable-fuchsia
flutter upgrade
```
### Step 2 - Provisioning SSH Keys to FImage
To start, generate a new set of SSH keys for the emulator. 
```bash
ssh-keygen
```
For the sake of organization, call the key `fimage_key`. Don't set a password for the keypair. You should see an  output similar to below.
```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/nmcain/.ssh/id_rsa): fimage_key   
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in fimage_key
Your public key has been saved in fimage_key.pub
The key fingerprint is:
SHA256:yJz40GaEI+pyfBaTgC9n2HGlGDBEBVYeLVV3PyCd99A nmcain@OptiPlex-790
The key's randomart image is:
+---[RSA 3072]----+
|=*=+o.o. o.o. .  |
|.o.+.=  . oooo E |
|. =.* .     .oo  |
| = = O o      .. |
|+ = * O S        |
|.=   B           |
|..o o .          |
|.. o             |
|                 |
+----[SHA256]-----+
```
Now that the key has been generated, send the public key to FImage. Make sure the emulator is not started, and use the ZBI tool to inject the key.

```bash
./tools/zbi -o init/fuchsia-ssh.zbi init/fuchsia.zbi --replace --entry data/ssh/authorized_keys=/home/$USER/.ssh/fimage_key.pub
```

### Step 3 - Starting and Checking FImage
Now that SSH and the SDK are configured, you can start FImage.
```bash
./network-config
./fimage-gui 4096
```
In a new terminal, check that the emulator is running and recognized by Flutter, using the `flutter devices` command.
```
nmcain@OptiPlex-790 ~/fimage$ flutter devices
3 connected devices:

fuchsia_fimage (null) • fe80::98bb:89e1:a5cf:daab%brqemu • fuchsia-x64    • Fuchsia 2021-05-26T01:49:18+00:00
Linux (desktop)       • linux                            • linux-x64      • Ubuntu 20.04.2 LTS 5.8.0-53-generic
Chrome (web)          • chrome                           • web-javascript • Google Chrome 91.0.4472.77
```
Your device is now ready to run Flutter apps!

### Step 4 - Preparing and Running a Flutter App
The instructions for this step can be found at [Preparing and Running a Flutter App >](flutter-fuchsia)
