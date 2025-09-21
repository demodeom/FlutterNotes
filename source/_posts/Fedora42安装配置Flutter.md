---
title: Fedora42安装配置Flutter
date: 2025-09-21 09:05:37
tags:
	- 环境搭建
categories:
	- Flutter
cover: https://s21.ax1x.com/2025/09/20/pV4wFqx.png
---



# Linux安装配置Flutter

**准备工作**

创建软件安装目录

```
mkdir ~/DevTools
```

**安装 Flutter**

1. 下载为 Linux 发行版准备的 flutter 压缩包，解压压缩包
2. 将解压之后的目录， 复制到 `~/DevTools` 目录

```
~/DevTools/flutter_linux_3.32.7-stable
```

**配置 Flutter 环境变量**

```bash
echo 'export FLUTTER_HOME=$HOME/DevTools/flutter_linux_3.32.7-stable/flutter' >> ~/.zshrc
echo 'export PATH=$PATH:$FLUTTER_HOME/bin' >> ~/.zshrc
```

**生效环境变量配置**

重启系统或者使用以下命令临时生效

```bash
source ~/.zshrc
```



使用以下命令诊断当前环境

```bash
flutter doctor
```



**clang++**

```
✗ clang++ is required for Linux development.
  It is likely available from your distribution (e.g.: apt install clang), or can be downloaded from https://releases.llvm.org/
```

```bash
sudo dnf install clang 
```

**CMake**

```
✗ CMake is required for Linux development.
  It is likely available from your distribution (e.g.: apt install cmake), or can be downloaded from 
```

```bash
sudo dnf install cmake 
```

**GTK 3.0**

```
✗ GTK 3.0 development libraries are required for Linux development.
  They are likely available from your distribution (e.g.: apt install libgtk-3-dev)
```

```bash
sudo dnf install gtk3-devel 
```

**ninja**

```
✗ ninja is required for Linux development.
  It is likely available from your distribution (e.g.: apt install ninja-build), or can be downloaded from
  https://github.com/ninja-build/ninja/releases
```

```bash
sudo dnf install ninja-build
```

**eglinfo**

```
! Unable to access driver information using 'eglinfo'.
  It is likely available from your distribution (e.g.: apt install mesa-utils)
```

```
sudo dnf install egl-utils
```

**完整命令**

```bash
sudo dnf install clang cmake gtk3-devel egl-utils ninja-build
```

**Android toolchain**

```
[!] Android toolchain - develop for Android devices (Android SDK version 36.0.0)
    ! Some Android licenses not accepted. To resolve this, run: flutter doctor --android-licenses
```



```bash
flutter doctor --android-licenses
```

看到以下提示，输入 `y`，然后按 `Enter` 键

```
Review licenses that have not been accepted (y/N)? 
```

看到以下提示，输入 `y`，然后按 `Enter` 键

```
Accept? (y/N): 
```

无错误输出

```
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, 3.32.7, on Fedora Linux 42 (Workstation Edition) 6.15.9-201.fc42.x86_64, locale en_US.UTF-8)
[✓] Android toolchain - develop for Android devices (Android SDK version 36.0.0)
[✓] Chrome - develop for the web
[✓] Linux toolchain - develop for Linux desktop
[✓] Android Studio (version 2025.1.2)
[✓] Proxy Configuration
[✓] Connected device (2 available)
[✓] Network resources

• No issues found!

```

