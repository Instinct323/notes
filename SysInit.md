# Windows

- Download → C:\
- tmp → C:\


# Ubuntu

- NTFS
  - ntfsfix /dev/*
  
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
