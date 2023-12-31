# SteamShowCase
![](Resources/Banner.png)

## Table of Contents
- [Download](https://github.com/RylexOff/SteamShowCase/releases/download/1.0.0/SteamShowCase.exe)
- [Exemple](#exemple)
- [Introduction](#introduction)
- [How it Works](#how-it-works)
- [Tutorial](#tutorial)
- [How to Compile](#how-to-compile)
- [System Requirements](#system-requirements)

## Exemple
<p align="center">
  <img src="https://github.com/RylexOff/SteamShowCase/blob/main/Resources/Preview.gif" alt="gif" />
</p>

## Introduction
SteamShowCase is a software that allows you to convert videos into GIFs and segment them into five parts, to beautify your Steam profile via the Workshop showcase.
This tool also aims to save you money because it's a free alternative to services like DeviantArt, which charge between €3 and €10 for this sort of thing 😂.

<h2>For best results, use 720p videos.</h2>

💫 Which gave me the idea to code : https://www.deviantart.com/tag/steamworkshop

Find video game or anime edits on YouTube easily with the following searches:
- For anime: "this is 4k anime [character name]"
- For games: "[Game name] [Character name] edit"
- For series: "[Series name] [Character name] edit"

## How it Works
SteamShowCase takes a video, converts it into a GIF, segments the GIF into five equal parts, and optimizes each to adhere to Steam's 5MB file size limit. It fine-tunes the GIFs by adjusting frame rates and optionally reducing quality, along with modifying the hex code to remove borders, ensuring a seamless display on your Steam profile. The gif will last maximum 10 seconds

  - FPS adjustment: Customize the frame rate according to your preference.
  - Quality control: Choose to maintain quality or reduce file size with an optional quality reduction.
  - Hex modification: The tool automatically adjusts the hex code of the GIFs to ensure compatibility with Steam's interface.

## Tutorial
Follow these steps to use SteamShowCase to create gifs and upload to Steam.

### Step 1: Prepare Your Video

- Find a video you want to use, for example, from YouTube (download at maximum 720P for optimal quality).
- Download the video to your computer. I recommend notube.net (be careful of the ad).

<p align="center">
  <img src="https://github.com/RylexOff/SteamShowCase/blob/main/Resources/Step%201.gif" alt="gif" />
</p>

### Step 2: Use SteamShowCase
Use SteamShowCase to convert your video file into a GIF.

- Donwload [SteamShowCase](https://github.com/RylexOff/SteamShowCase/releases/tag/1.0.0)
- Click on 'Convert Video'.
- Select your video file.
- Click on 'Select Output Folder'.
- Select your Output folder.
- Choose your configuration.
- Click on 'Start'. it may take a minute. The gif will last maximum 10 seconds

<p align="center">
  <img src="https://github.com/RylexOff/SteamShowCase/blob/main/Resources/Step%202.gif" alt="gif" />
</p>

### Step 3 : Upload to steam

- Go to [Steam Community Shared files](https://steamcommunity.com/sharedfiles/edititem/767/3/)
- Name GIFs by their number to easily locate them , Exemple : '8-1' (For the 8th gif part 1).
- Select gif , Exemple 'segment_1.gif'.
- Inspect element and click on the console tab.
- Past ```$J('[name=consumer_app_id]').val(480);$J('[name=file_type]').val(0);$J('[name=visibility]').val(0);``` and press enter .This is to make Steam believe that it is a workshop object and not an artwork (IMPORTANT).
- Check the box: 'I certify that I am the person who created this content'
- Click on 'Save and continue'.

<p align="center">
  <img src="https://github.com/RylexOff/SteamShowCase/blob/main/Resources/Step%203.gif" alt="gif" />
</p>

### Step 4 : Comming Soon

## How to Compile

If you wish to compile the program yourself, here are the methods:

### Script Version (Easy)

**Note:** You must have Python installed.

Simply launch:

On Linux:
```bash
./run.sh
```

On Windows:
```batch
run.bat
```

### PyInstaller Version with Pre-compiled Bootloader

Install PyInstaller if it's not already installed:
```bash
pip install pyinstaller
```

Then compile the project:
```bash
pyinstaller --onefile --icon=favicon.ico --noconsole SteamShowCase.py
```
If you encounter an error, specify the path:
```bash
YourPATH\python310\Scripts\pyinstaller.exe --onefile --icon=favicon.ico --add-data "SteamShowCaseLogo.png;." --distpath . --noconsole SteamShowCase.py
```

### PyInstaller Version with Bootloader

Clone the PyInstaller repository or download the development branch as a zip:
```bash
git clone https://github.com/pyinstaller/pyinstaller.git
# Or
# Download https://github.com/pyinstaller/pyinstaller/archive/refs/heads/develop.zip and extract it into a folder
```

Navigate to the bootloader directory and build the bootloader:
```bash
cd pyinstaller/bootloader
python ./waf all
```

Navigate back to the root directory of PyInstaller, uninstall any existing installation, upgrade tools, and install:
```bash
cd ..
pip uninstall pyinstaller
pip install --upgrade pip setuptools wheel
sudo pip install .
```

Finally, compile your project:
```bash
cd path/to/SteamShowCase
pyinstaller --onefile --icon=favicon.ico --noconsole SteamShowCase.py
```

## System Requirements
- Windows 10 or 11 X64
- I thinks it works on linux with wine


