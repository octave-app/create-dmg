# create-dmg

A little program to build fancy DMGs, for Octave.app.

## Status and contribution policy

This is a project fork of andreyvit's create-dmg project at <https://github.com/andreyvit/create-dmg>, modified to support [Octave.app](https://github.com/octave-app)'s needs. It has diverged from upstream, and we (the Octave.app folks) don't expect our changes to make it back upstream, since there has been no activity on the upstream project since 2015.

This project is maintained by the Octave.app group, primarily for our own internal use. Contributions are welcome, but we don't primarily maintain this

## Installation

Create-dmg is a set of scripts written in shell and Python. Download it by cloning the [create-dmg repo from GitHub](https://github.com/octave-app/create-dmg). Then you can run the `create-dmg` command directly from there.

```text
git clone https://github.com/octave-app/create-dmg

cd create-dmg
./create-dmg [options ...] <target.dmg> <source_folder>
```

You'll probably want to add it to your `$PATH` so you can run it from any directory.

Create-dmg requires Python 3. Newer versions of macOS (like, 12.3 and later) come with Python 3. On older macOS versions, you'll need to install it. The Xcode command line tools include Python 3, so if you install those, that'll cover it.

## Usage

```text
create-dmg [options ...] <target.dmg> <source_folder>
```

All contents of *source\_folder* will be copied into the disk image *target.dmg*.

### Options

* **--volname \<name>**: set volume name (displayed in the Finder sidebar and window title)
* **--volicon \<icon.icns>**: set volume icon
* **--background \<pic.png>**: set folder background image (provide png, gif, jpg)
* **--window-pos \<x> \<y>**: set position the folder window
* **--window-size \<width> \<height>**: set size of the folder window
* **--text-size \<text_size>**: set window text size (10-16)
* **--icon-size \<icon_size>**: set window icons size (up to 128)
* **--icon \<file_name> \<x> \<y>**: set position of a file's icon
* **--hide-extension \<file_name>**: hide the extension of file
* **--custom-icon <file_name>/\<custom_icon>/\<sample_file> \<x> \<y>**: set position and custom icon
* **--app-drop-link \<x> \<y>**: make a drop-target link to Applications, at location (x, y)
* **--eula \<eula_file>**: attach a license file to the dmg
* **--internet-enable**: enable automatic mount & copy (probably broken on newer macOS versions)
* **--no-internet-enable**: disable automatic mount & copy (this is the default)
* **--add-file \<target_name> \<source_file_path> \<x> \<y>**: add additional file (option can be used multiple times)
* **--disk-image-size \<n>**: set the disk image size manually to n MB
* **--version**: display version information for this tool
* **-h**, **--help**, **-?**: display the help screen

## Examples

```shell
#!/bin/bash
rm -f Application-Installer.dmg
create-dmg \
  --volname "Application Installer" \
  --volicon "application_icon.icns" \
  --background "installer_background.png" \
  --window-pos 200 120 \
  --window-size 800 400 \
  --icon-size 100 \
  --icon Application.app 200 190 \
  --hide-extension Application.app \
  --app-drop-link 600 185 \
  Application-Installer.dmg \
  my_source_folder/
```

## Other DMG-building resources

These are some other DMG-building tools. They're not related to this project, but they have served as inspiration, and you may find useful.

* [node-appdmg](https://github.com/LinusU/node-appdmg)
  * May be more powerful than create-dmg, but doesn't have all the same features and requires Node.js.
* [dmgbuild](https://pypi.python.org/pypi/dmgbuild)

And here's some online info.

* ["How do I create a nice DMG?" question on StackOverflow](http://stackoverflow.com/questions/96882/how-do-i-create-a-nice-looking-dmg-for-mac-os-x-using-command-line-tools)
