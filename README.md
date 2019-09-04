# Installation of a developers MacOS machine

So this month I started working at Frontmen. I got a new MacBook Pro and wanted to install and configure my machine. I thought of all the tooling I needed to install, and the configurations I did on other Macs.

Installation of apps like: Slack and VSCode, and non graphical apps like: Node and git. The problem here is obvious: I don't want to go through the process of 1) Finding the application on a website 2) Configuring the non-graphical application 3) Removing the dmg file.

Of course the follwing is just my preference, you can alter as you like.

---

# Application installation using brew

To automate the process a little bit I started using brew. Brew is a tool that lets you install software from the terminal. Once all the apps are installed you can use [Homebrew Bundle](https://github.com/Homebrew/homebrew-bundle) to bundle all the installed apps in one file and use it as input for the installation of a MacOS machine.

# Brew Casks vs Formulae

First install brew as shown on the [homepage](https://brew.sh/) (installs also Xcode Command Line Tools (including Git)).

Lets say we want to install iTerm. We search for its name as follows: `brew search telegram` (Telegram is a communication platform like WhatsApp). You can see the results listed under two categories, one being: `Formulae` and the other category: `Casks`. As you can see the non-graphical telegram-cli (command line interface) is listed under `Formulae` and the graphical telegram is listed under `Casks`. 

---

> `brew search app-name` lets you search for an app inside the repositories. 

> `Formulae` are apps without a graphical interface. `Casks` are apps with a graphical interface.

# Casks for Web Development

`brew cask install iterm2 cyberduck google-chrome hyperswitch postman spotify slack telegram visual-studio-code flux spectacle appcleaner enpass teamspeak-client teamviewer`

1. iTerm: alternative terminal with lots of configuration options
2. Cyberduck: is a libre server and cloud storage browser for Mac and Windows with support for FTP, SFTP, WebDAV, Amazon S3, OpenStack Swift, Backblaze B2, Microsoft Azure & OneDrive, Google Drive and Dropbox
3. HyperSwitch: enables you swap between all application windows using `cmd+tab`
4. Postman: is a great tool when trying to dissect RESTful APIs made by others or test ones you have made yourself
5. Flux: makes the color of your computer's display adapt to the time of day, warm at night and like sunlight during the day.
6. Spectacle: Move and resize windows with ease using shortcuts like `cmd+option+left-arrow`
7. AppCleaner: is a small application which allows you to thoroughly uninstall unwanted apps


## Configure quick access to iTerm

Alternative terminal with loads of configuration options.

1. Go to Preferences (`cmd+,`)
2. Go to Profiles
3. Go to the subtab Keys
4. Click Configure Hotkey Window
5. Set a hotkey (mine is `cmd+shift+l`)
6. Go to the subtab Window
7. Set the style dropdown to: `Full-Width Bottom of Screen`
8. Change the `transparancy` as you like

## Google Chrome Extensions

From most to least used:

1. [uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm) uses the [least amount of memory](https://github.com/gorhill/uBlock/wiki/uBlock-vs.-ABP:-efficiency-compared)
2. [Switch Tabs](https://chrome.google.com/webstore/detail/alt-%20-q-switch-tabs-keybo/odhjcgnlbagjllfbilicalpigimhdcll) lets you switch between the last used tab. This is useful when you have lots of tabs open and you don't want to search.
3. [Vimium](https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb) vim for browsing the web, and quikcly accessing form inputs.
4. [The Great Suspender](https://chrome.google.com/webstore/detail/the-great-suspender/klbibkeccnjlkjkiokjodocebajanakg) suspends Chrome tabs when you don't use them.
5. [JSON Formatter](https://github.com/callumlocke/json-formatter) extension for printing JSON and JSONP nicely when you visit it 'directly' in a browser tab.
6. [Quick QR Code Generator](https://chrome.google.com/webstore/detail/quick-qr-code-generator/afpbjjgbdimpioenaedcjgkaigggcdpp)
is nice to have for when you want to read further on your mobile phone.
7. [Session Buddy](https://chrome.google.com/webstore/detail/session-buddy/edacconmaakjimmfgnblocblbcdcpbko) lets you save your current open tabs for later use.

# Formulae for Web Development

`brew install fish node@10 thefuck docker`

1. Fish: is a smart and user-friendly command line shell for Linux, macOS, and the rest of the family
2. Node: JavaScript runtime built on Chrome V8
3. TheFuck: corrects errors in previous console commands
4. Docker: Build, Share, and Run Any App, Anywhere

## Configure fish shell

### **Fish shell as default shell**

1. `sudo vim /etc/shells`
2. Add `/usr/local/bin/fish` to shells (so you can change shell using `chsh`)
3. `chsh -s /usr/local/bin/fish`

### **Fisher package manager**

There is also a package manager for Fish, called Fisher. At the time of writing Fisher can't be installed using brew. To install it please go to the [Github page](https://github.com/jorgebucaran/fisher).

You can add awesome fish packages using: `fisher add fish-package`

### **Directory jumping**

Changes directory based upon a hidden score z gives to the directories you navigate to. 

`fisher add jethrokuan/z`

After installation & usage:
1. Change directory to a couple of directories: `cd ~/.ssh`, `cd /users/bramgroothedde`
2. `z bram` followed by `tab`
3. Changes directory to `/users/bramgroothedde`

### **Fish SpaceFish-package** 

To customize the promt of the Fish shell you can use [SpaceFish](https://github.com/matchai/spacefish). SpaceFish can be installed using Fisher with the command: `fisher add matchai/spacefish`.

### **Other**

For more awesome Fish stuff see [this repository](https://github.com/jorgebucaran/awesome-fish).

## Configure TheFuck alias

1. `thefuck --alias ez > ~/.config/fish/functions/ez.fish`
Install z for directory jumping: 

# Manual MacOS configurations

Dock:
- Remove not needed icons from the Dock
- Right-click dock -> dock preferences
    - Position on screen LEFT

System Preferences:
- TouchId middle finger
- Keyboard
    - Key Repeat FAST
    - Delay Until Repeat SHORT
    - To disable accentuated char suggestion run the following in a terminal (being able to hold key and output the key): defaults write -g ApplePressAndHoldEnabled -bool false
- Trackpad
    - Point & Click
        - Tap to click ON
- Accessibility
    - Mouse & Trackpad
        - Trackpad Options
            - Enable dragging ON | THREE FINGER DRAG
- Desktop & Screen Saver
    - Screen Saver
        - Hot Corners
            - Lock Screen
- Security & Privacy
    - General
        - Require password IMMEDIATELY
- Energy Saver
    - Turn display off after 10MINUTES














