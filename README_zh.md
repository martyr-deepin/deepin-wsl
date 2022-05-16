# DeepinWSL

[English readme](./README.md)

[中文文档](./README_zh.md)

本项目基于 [wsldl](https://github.com/yuk7/wsldl)

### [查看详细文档](https://git.io/wsldl-doc)

## 💻要求
* 大于或等于 Windows 10 1709 Fall Creators Update 版本(x64/arm64)。
* 必须开启 Windows Subsystem for Linux 功能。

## 📝如何去使用
#### exe 的用法
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

#### 只运行 exe 程序
```cmd
>Deepin.exe
[root@PC-NAME user]#
```

#### 带参数运行
```cmd
>Deepin.exe run uname -r
4.4.0-43-Microsoft
```

#### 使用带有路径翻译的参数
```cmd
>Deepin.exe runp echo C:\Windows\System32\cmd.exe
/mnt/c/Windows/System32/cmd.exe
```

#### 更改默认用户（需要先新建盖用户）
```cmd
>Deepin.exe config --default-user user

>Deepin.exe
[user@PC-NAME dir]$
```

#### 设置 Windows Terminal 作为默认终端
```cmd
>Deepin.exe config --default-term wt
```

#### 如何卸载
```cmd
>Deepin.exe clean

```

#### 如何备份
export to backup.tar.gz (WSL1 or 2)
```cmd
>Deepin.exe backup --tgz
```
export to backup.ext4.vhdx.gz  (WSL2 only)
```cmd
>Deepin.exe backup --vhdxgz
```

#### 如何导入
.tar(.gz)  (WSL1 or 2)
```cmd
>Deepin.exe install backup.tar.gz
```
.ext4.vhdx(.gz)  (WSL2 only)
```cmd
>Deepin.exe install backup.ext4.vhdx.gz
```

## 📄许可证
[MIT](LICENSE.md)

Copyright (c) 2017-2021 [yuk7](https://github.com/yuk7)

**非常感谢 [yuk7](https://github.com/yuk7/) 的贡献, 让我们可以轻松的构建 WSL 发行版**
