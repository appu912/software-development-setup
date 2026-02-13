# Gnome Terminal Dracula Theme Setup

## Dracula Theme

1. We'll use [this](https://draculatheme.com/gnome-terminal) theme for our gnome terminal.
2. First we'll install the dconf-cli to interact with the key/value dconf database in ubuntu.
    
    ```bash
    sudo apt install dconf-cli
    ```
3. Now we'll clone the gnome-terminal repo and install the theme.
    
    ```bash
    git clone https://github.com/dracula/gnome-terminal
    cd gnome-terminal
    ./install.sh
    ```
4. Finally we'll install the JetBrains Mono font.
    ```bash
    sudo apt install fonts-jetbrains-mono
    ```
5. Now go to terminal preference -> Default profile -> Custom Fonts -> JetBrains Mono(14) and then restart the terminal.
