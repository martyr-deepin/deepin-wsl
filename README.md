# DeepinWSL

[English readme](./README.md)

[中文文档](./README_zh.md)

Deepin on WSL (Windows 10 FCU or later)
base on [wsldl](https://github.com/yuk7/wsldl)

### [Detailed documentation is here](https://git.io/wsldl-doc)

## 💻Requirements
* Windows 10 1709 Fall Creators Update or later(x64/arm64).
* Windows Subsystem for Linux feature is enabled.

## 📝How-to-Use(for Installed Instance)
#### exe Usage
```
Usage :
    <no args>
      - Open a new shell with your default settings.

    run <command line>
      - Run the given command line in that instance. Inherit current directory.

    runp <command line (includes windows path)>
      - Run the given command line in that instance after converting its path.

    config [setting [value]]
      - `--default-user <user>`: Set the default user of this instance to <user>.
      - `--default-uid <uid>`: Set the default user uid of this instance to <uid>.
      - `--append-path <true|false>`: Switch of Append Windows PATH to $PATH
      - `--mount-drive <true|false>`: Switch of Mount drives
      - `--wsl-version <1|2>`: Set the WSL version of this instance to <1 or 2>
      - `--default-term <default|wt|flute>`: Set default type of terminal window.

    get [setting]
      - `--default-uid`: Get the default user uid in this instance.
      - `--append-path`: Get true/false status of Append Windows PATH to $PATH.
      - `--mount-drive`: Get true/false status of Mount drives.
      - `--wsl-version`: Get the version os the WSL (1/2) of this instance.
      - `--default-term`: Get Default Terminal type of this instance launcher.
      - `--lxguid`: Get WSL GUID key for this instance.

    backup [contents]
      - `--tar`: Output backup.tar to the current directory.
      - `--tgz`: Output backup.tar.tar to the current directory.
      - `--vhdx`: Output backup.ext4.vhdx to the current directory. (WSL2 only)
      - `--vhdxgz`: Output backup.ext4.vhdx.gz to the current directory. (WSL2 only)
      - `--reg`: Output settings registry file to the current directory.

    clean
      - Uninstall that instance.

    help
      - Print this usage message.
```

#### Just Run exe
```cmd
>Deepin.exe
[root@PC-NAME user]#
```

#### Run with command line
```cmd
>Deepin.exe run uname -r
4.4.0-43-Microsoft
```

#### Run with command line with path translation
```cmd
>Deepin.exe runp echo C:\Windows\System32\cmd.exe
/mnt/c/Windows/System32/cmd.exe
```

#### Change Default User(id command required)
```cmd
>Deepin.exe config --default-user user

>Deepin.exe
[user@PC-NAME dir]$
```

#### Set "Windows Terminal" as default terminal
```cmd
>Deepin.exe config --default-term wt
```

#### How to uninstall instance
```cmd
>Deepin.exe clean

```

#### How-to-backup
export to backup.tar.gz (WSL1 or 2)
```cmd
>Deepin.exe backup --tgz
```
export to backup.ext4.vhdx.gz  (WSL2 only)
```cmd
>Deepin.exe backup --vhdxgz
```

#### How-to-import
.tar(.gz)  (WSL1 or 2)
```cmd
>Deepin.exe install backup.tar.gz
```
.ext4.vhdx(.gz)  (WSL2 only)
```cmd
>Deepin.exe install backup.ext4.vhdx.gz
```

## 📄License
[MIT](LICENSE.md)

Copyright (c) 2017-2021 [yuk7](https://github.com/yuk7)

**Thanks to [yuk7](https://github.com/yuk7/)'s contribution, so that we can easily build our own WSL distribution.**
