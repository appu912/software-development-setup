# xclip Setup for Ubuntu

*xclip can be used for copying/pasting text on and from clipboard.*

## Installation

1. You can install xclip using the Advanced Package Tool (apt).
    
    ```bash
    sudo apt update
    sudo apt upgrade
    sudo apt install xclip
    ```
2. Now xclip is installed in your system-wide binaries (`/usr/bin/xclip`).

## Configuring xclip

1. Now `xclip` command is quite verbose. So we will replace it using `pbcopy/pbpaste`.
2. Add the below lines to your `~./bashrc` file.
    
    ```bash
    alias pbcopy='xclip -selection clipboard'
    alias pbpaste='xclip -selection clipboard -o'
    ```
3. Now we can use pbcopy and pbpaste for copying and pasting stuff to clipboard.
    
    ```bash
    pbcopy < file1.txt
    pbpaste > file2.txt
    ```
