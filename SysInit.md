# Windows

- Download → C:\
- tmp → C:\

# Ubuntu
  
- /etc/fstab
  - RUN: ntfsfix /dev/*
  - /dev/disk/by-uuid/* /media/user/* ntfs defaults 0 2

- ~/.bashrc
  - export LANG=en_US
  - export LANGUAGE=en_US
  - export PATH=$PATH:~/.local/bin
  
- /etc/default/grub
  - GRUB_DEFAULT=2
  - RUN: update-grub
  
- /etc/ppp/options
  - lcp-echo-interval
  - lcp-echo-failure
