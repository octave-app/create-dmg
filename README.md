create-dmg
==========

A little program to build fancy DMGs.  

This is a project fork of andreyvit's create-dmg project at <https://github.com/andreyvit/create-dmg>, modified to support [Octave.app](https://github.com/octave-app)'s needs. It has diverged from upstream, and we don't expect our changes to make it back upstream, since there has been no activity on the upstream project since 2015.

## Status and contribution policy

This project is maintained by the Octave.app group, primarily for our own internal use. Contributions are welcome, but we don't primarily maintain this

## Installation

Create-dmg is a set of scripts written in shell and Python. Download it by cloning the repo or downloading a zip file from our Releases page and extracting it. Then you can run the `create-dmg` command directly from there.

```text
git clone https://github.com/octave-app/create-dmg
cd create-dmg
./create-dmg [options ...]
```  

## Usage

> create-dmg [options...] [output\_name.dmg] [source\_folder]  

All contents of source\_folder will be copied into the disk image.  

#### Options

*   **--volname [name]:** set volume name (displayed in the Finder sidebar and window title)  
*   **--volicon [icon.icns]:** set volume icon    
*   **--background [pic.png]:** set folder background image (provide png, gif, jpg)    
*   **--window-pos [x y]:** set position the folder window    
*   **--window-size [width height]:** set size of the folder window    
*   **--text-size [text size]:** set window text size (10-16)    
*   **--icon-size [icon size]:** set window icons size (up to 128)    
*   **--icon [file name] [x y]:** set position of the file's icon    
*   **--hide-extension [file name]:** hide the extension of file    
*   **--custom-icon [file name]/[custom icon]/[sample file] [x y]:** set position and custom icon    
*   **--app-drop-link [x y]:** make a drop link to Applications, at location x, y    
*   **--eula [eula file]:** attach a license file to the dmg    
*   **--no-internet-enable:** disable automatic mount&copy    
*   **--add-file [target name] [path to source file] [x y]:** add additional file (option can be used multiple times)    
*   **--disk-image-size [x]:** set the disk image size manually to x MB    
*   **--version:** show tool version number    
*   **-h, --help:** display the help  


##  Example

```shell
#!/bin/ss
test -f Application-Installer.dmg && rm Application-Installer.dmg  
create-dmg \  
  --volname "Application Installer" \  
  --volicon "application\_icon.icns" \  
  --background "installer\_background.png" \  
  --window-pos 200 120 \  
  --window-size 800 400 \  
  --icon-size 100 \  
  --icon Application.app 200 190 \  
  --hide-extension Application.app \  
  --app-drop-link 600 185 \  
  Application-Installer.dmg \  
  source\_folder/
```


## Other DMG-building projects

* [node-appdmg](https://github.com/LinusU/node-appdmg)
* [dmgbuild](https://pypi.python.org/pypi/dmgbuild)
* see the [StackOverflow question](http://stackoverflow.com/questions/96882/how-do-i-create-a-nice-looking-dmg-for-mac-os-x-using-command-line-tools)
