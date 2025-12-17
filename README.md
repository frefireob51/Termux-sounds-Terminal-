### Termux Terminal                                                                       
Termux Android Banner & Customization
Personalize your Termux terminal with custom ASCII banners, hacker-style boot screens, typing animations, and sound effects. Fully customizable Bash scripts for Android terminal enthusiasts.
Termux is an Android terminal emulator and Linux environment that runs without root.
This project adds a custom banner and optional hacker-style boot effects:

Custom ASCII art banner

Typing animation effect

Boot sounds (.mp3 via mpv)

ANSI color support

Fully configurable via Bash scripts


Perfect for terminal customization, learning Bash scripting, and adding a hacker vibe to your Android terminal.

### 🌿 Termux Music Boot & Command Sound (Android)
Customize your Termux Android terminal with music on startup and sound after every command.
This setup uses mpv to play MP3 files stored in your Termux storage directory.
### 1️⃣ Update package lists
Fetches the latest list of available packages and versions.
Does not upgrade packages yet.

### 📁 Termux Storage Commands
Grant Storage Permission
Before accessing storage, you need permission:
```
termux-setup-storage
```
```
pkg update && pkg upgrade
```
### 🔐 Sound Rules for Termux Startup & Commands

Please follow these rules carefully to ensure sounds work properly in Termux.


---

### 📂 Required Sound Directory

All sound files must be placed in this directory:

/data/data/com.termux/files/home/storage

⚠️ Do not change this directory, otherwise sounds will not work.

### 🎧 Sound Files & Purpose

1️⃣ Termux Startup Typing Sound

🟢 When Termux starts, text is displayed letter by letter and this sound is played:

howareyou.mp3

✔ Used for startup typing animation
✔ Plays automatically when Termux launches

2️⃣ Command Enter Sound

### 🔊 When you press Enter after any command, this sound is played:
For example ls,cd,mv,etc any cmd


✔ Plays on every command execution

### 📛 File Naming Rules (Very Important)

✔ File names must match exactly
✔ Use lowercase letters only
✔ Extension must be .mp3

❌ Do not rename the files
❌ Do not use capital letters
❌ Do not add extra spaces

### 🔁 Replace With Your Own Sounds

You can use your own MP3 files, just follow the rules:

Place your MP3s in the correct directory

Rename them to:

howareyou.mp3 for startup sound

sound.mp3 for command sound

### 🔊 Test Command

To test the command sound:

mpv --no-terminal /data/data/com.termux/files/home/storage/sound.mp3

If you hear the sound → setup is correct ✅



### Command for Termux 
```
nano ~/.bashrc
```
### Command for Kali Linux 
```
nano ~/.zshrc
```
###  
```
