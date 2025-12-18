### Termux Terminal                                                     🚀 Termux Customization: Hacker-Style Terminal 🎶💻

Personalize your Termux terminal with custom ASCII banners, hacker-style boot screens, typing animations, and sound effects. Fully customizable Bash scripts for Android terminal enthusiasts.

Termux is an Android terminal emulator and Linux environment that runs without root.

This project adds a custom banner and optional hacker-style boot effects:

✨ Features

🖼 Custom ASCII Art Banner – Show your personalized banner on startup

⌨️ Typing Animation Effect – Text appears letter by letter

🎶 Boot Sounds – Play .mp3 files using MPV

🌈 ANSI Color Support – Fancy green, red, and colored text

🛠 Fully Configurable – Customize everything via Bash scripts                  
Termux Android Banner & 
### 🌿 Termux Music Boot & Command Sound (Android)
Customize your Termux Android terminal with music on startup and sound after every command.
This setup uses mpv to play MP3 files stored in your Termux storage directory.
### 📁 Termux Storage Commands
Grant Storage Permission
Before accessing storage, you need permission:
```
termux-setup-storage
```
### ✅ Update package lists
Fetches the latest list of available packages and versions.
Does not upgrade packages yet.
```
pkg update && pkg upgrade
```

### ⚡ Install MPV for Termux Sound Playback

To enable startup and command sounds in Termux, you need the MPV media player.
 Install MPV

Run this command in Termux:
```
pkg install mpv
```
Installs MPV, a lightweight audio/video player compatible with Termux

Required to play your howareyou.mp3 (startup) and sound.mp3 (command) files

### 🔐 Sound Rules for Termux Startup & Commands

Please follow these rules carefully to ensure sounds work properly in Termux.

### 📂 Required Sound Directory

All sound files must be placed in this directory:

/data/data/com.termux/files/home/storage

⚠️ Do not change this directory, otherwise sounds will not work.

### 🎧 Sound Files & Purpose

  Termux Startup Typing Sound

🟢 When Termux starts, text is displayed letter by letter and with sound 

How are you 

✔ Used for startup typing animation
✔ Plays automatically when Termux launches

 🔊 Command Enter Sound

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

### 🔊 Sound Test Command

If an .mp3 file exists in the following directory:

```
cd /data/data/com.termux/files/home/storage
```
then the sound system is correctly set up and audio will play when you run this command:
```
mpv --no-terminal /data/data/com.termux/files/home/storage/sound.mp3
```
### ✅ What This Means

If you hear sound → MPV is installed and working

The file path is correct

Termux has access to storage

Your command sound feature will work properly


### ⚠️ Important Notes

The file must exist in the directory

The file name must be exactly sound.mp3

Only .mp3 format is supported


If no sound plays, check:

MPV installation (pkg install mpv)

Storage permission (termux-setup-storage)



### 🛠 Steps to Edit
```
nano ~/.bashrc
```
And Paste this code 👇 and save this code CTRL x and y enter 
```
clear

# Welcome sound
nohup mpv --no-terminal ~/storage/howareyou.mp3 >/dev/null 2>&1 &
disown   # <-- hide [1]+ Done

# Auto typing text
text="How are you ❤️"
for ((i=0; i<${#text}; i++)); do
  printf "%s" "${text:$i:1}"
  sleep 0.08
done
echo ""

# Play sound after every command
function play_sound_after_command() {
    # Kill previous sound if still running
    pkill -f "mpv --no-terminal ~/storage/sound.mp3" 2>/dev/null
    
    # Play new sound in background and disown
    nohup mpv --no-terminal ~/storage/sound.mp3 >/dev/null 2>&1 &
    disown   # <-- hide [2]+ Done
}

PROMPT_COMMAND="play_sound_after_command"
```

[![YouTube](https://img.shields.io/badge/YouTube-🔥TermuxMastery🔥-ff0000?style=for-the-badge&logo=youtube&logoColor=ffffff)](https://youtube.com/@termuxmastery?si=U8LvcGiAJZES7YHE)


