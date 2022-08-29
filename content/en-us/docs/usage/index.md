---
title: 'Instructions'
date: 2019-02-11T19:30:08+10:00
draft: false
weight: 4
summary: " "
---
 


Assuming there is a local git workspace /tmp/workdir

### #Enter the local workdir
```sh
cd /tmp/workdir
````
### #Initialize Remote Transparent Encryption Configuration

The first time you use gitl, you need to initialize the repository.

```sh
gitl initc
````
Or:

```
gitl initc -p your_passwd
```

> Remote Transparent Encryption supports two encryption methods:
>1. Automatically generate key file
>2. Password

>No human intervention is required during encryption and decryption. **Need to keep the key file**

### #export key

Export remote transparent encryption key for unlocking operation  

```sh
gitl export-key to-path
```


### #Decrypt repository

If the newly cloned repository has been encrypted, a decryption operation is required.

```sh
gitl unlock -p your_passwd
```
Or:
```sh
gitl unlock -k key_path
```

> Only one decryption operation is required!


### #Mark files as transparently encrypted
```sh
gitl encrypt -r plain.md
````

### #Mark files as locally encrypted
```sh
gitl encrypt plain.md -l -p passwd_for_this_file 
```

### #local decryption
```sh
gitl decrypt plain.md -l -p passwd_for_this_file
```

### #Remote decryption
```sh
gitl decrypt -r plain.md
```
