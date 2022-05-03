---
categories: ["Git"]
tags: ["Git", "tool"]
title: "Git SSH"
linkTitle: "Git SSH"
date: 2022-05-03
description: >
  Relevant operation records of Git SSH.
---

{{% pageinfo %}}
Applicable to multiple Git accounts.
{{% /pageinfo %}}

## Git SSH

1. Enter`Win+R`and run `bash` on Windows, there's no special on Linux.

   ```shell
   cd ~/.ssh
   ```

2. Generate key.

   ```shell
   ssh-keygen -t rsa -C "0123456@mail.com"
   ```

3. Copy the content of file`fff.pub` into GitHub.

4. Add the private key.

   ```shell
   ssh-agent bash
   ssh-add ~/.ssh/ffff
   ```

5. Create a file named `config` in the `~/.ssh` directory.

   ```
   Host xxx.github.com
   HostName github.com
   IdentityFile ~/.ssh/ffff
   PreferredAuthentications publickey
   User XXX
   ```

6. Connection test.

   ```shell
   ssh -T git@xxx.github.com
   ```

7. Exit.

   ```shell
   exit
   ```
   
8. For security, if you migrate to another computer, don't forget to delete the key files.

## Clone

```shell
git clone git@github.com:yyyyyyyyyyyy
```

Change to

```shell
git clone git@xxx.github.com:yyyyyyyyyyyy
```

