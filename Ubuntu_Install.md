# Install Ubuntu 18.04_LTS

Please read official document:

[Install Ubuntu dektop](https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-desktop#5)

Or other tutorials:

[How To Install Ubuntu](https://purplemonkeydishwasher.co.uk/2019/01/30/the-ubuntu-installation-guide/)

# Recovery of chcuk03

Following the installation guide but in Step 6.

## Allocate drive space

![img](https://tutorials.ubuntu.com/es6-bundled/src/codelabs/tutorial-install-ubuntu-desktop/img/8d4c3c33957b4ef.png)

1. Choose **'Something  else'**

2. Disk partition for Ubuntu

   ```shell
   Filesystem      Size   Mounted on
   /dev/nvme0n1p1  256M   /boot/efi   # Just choose whole disk, do not choose partition
   /dev/nvme0n1p5  500M   /boot
   /dev/nvme0n1p6  16G    swap area
   /dev/nvme0n1p7  66G   /   # the rest room for /
   /dev/nvme0n1p8  100G   /home
   ```

3. Disk parameters

   ![Root fs parameters](https://i.stack.imgur.com/f9AS5.png)

4. Notes

   如果系统损坏，把以上分区重新挂载然后重新安装， 在/home下的数据并不会有损失。

   