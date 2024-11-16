## 安装WSL2全流程

## 自动安装
```
# 查看分发系统并安装
wsl -l -o  # wsl --list --online

# 安装
wsl --install -d Ubuntu-20.04


```

## 手动
```
# 控制面版 》 程序和功能 子菜单 打开或关闭Windows功能 》 选择“适用于Linux的Windows子系统”与 “虚拟机平台”与“Hyper-V" 》 点击“确定”并重启

# 对于win11,这个其实也不用安装，是我搜网上教程看到地，执行
wsl --update

# 将 WSL 默认版本设置为 WSL 2
wsl --set-default-version 2

# 查询安装的系统
wsl -l -v

# 下载发行版本
Invoke-WebRequest -Uri https://aka.ms/wslubuntu2204 -OutFile Ubuntu.appx -UseBasicParsing
or
curl.exe -L -o ubuntu-2004.appx https://aka.ms/wslubuntu2004

# 安装 
Add-AppxPackage .\Ubuntu.appx

```
### 其他操作
```
# 进入系统
wsl -d Ubuntu1

# 设置默认系统
wsl --set-default Ubuntu1 # 或wsl -s Ubuntu1

# 导出镜像
wsl --export Ubuntu D:\WSL1\ubuntu.tar

# 导入镜像
wsl --import <导入Linux名称> <导入盘的路径>  版本(代表wsl2)
wsl --import-in-place ubuntu2004 D:\WSL\ext4.vhdx --version 2

# 取消C盘安装
wsl -t -d Ubuntu #或 wsl --shutdown
wsl --unregister Ubuntu


```
