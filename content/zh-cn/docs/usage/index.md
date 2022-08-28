---
title: '使用'
date: 2019-02-11T19:30:08+10:00
draft: false
weight: 4
summary: " "
---
 


假设有本地git工作区/tmp/workdir

### #进入本地仓库
```sh
cd /tmp/workdir
````
### #初始化远程透明加密配置

第一次使用gitl,需要对仓库进行初始化操作.

```sh
gitl cryptinit
````
或者:

```
gitl cryptinit -p your_passwd
```


>远程透明加密支持两种加密方式:
>1. 自动生成key文件
>2. 密码

>在加密和解密时不需要人工干预. **需要保管好key文件**

### #导出Key

导出远程透明加密key,用于解锁操作:  

···sh
gitl export-key to-path
···

### #解密仓库

如果新克隆的仓库已经被加密, 需要一次解密操作.

```sh
gitl unlock -p your_passwd
```
或者:
```sh
gitl unlock -k key_path
```

> 仅仅需要一次解密操作!


### #将文件标记为透明加密
```sh
gitl encrypt -r plain.md
````

### #将文件标记为本地加密
```sh
gitl encrypt plain.md -l -p passwd_for_this_file 
```

### #本地解密
```sh
gitl decrypt plain.md -l -p passwd_for_this_file
```

### #远程解密
```sh
gitl decrypt -r plain.md
```