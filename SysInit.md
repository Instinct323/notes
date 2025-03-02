# Windows

- MOD env: Download, tmp
- MOD time-sync: ntp.aliyun.com
- MOD virtual-memory:  0.125 ~ 3 RAM

# Ubuntu
  
- /etc/fstab
  - RUN: ntfsfix /dev/*
  - ADD: /dev/disk/by-uuid/* /media/user/* ntfs defaults 0 2

- ~/.bashrc
  - ADD: export LANG=en_US
  - ADD: export LANGUAGE=en_US
  - ADD: export PATH=$PATH:~/.local/bin
  
- /etc/default/grub
  - MOD: GRUB_DEFAULT=2
  - RUN: update-grub
  
- /etc/ppp/options
  - DEL: lcp-echo-interval
  - DEL: lcp-echo-failure
