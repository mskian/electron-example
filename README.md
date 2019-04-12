# Electron Linux Desktop APPlication

Convert your website/blog into Desktop Application Build using Electron (Currently Build Package Available for Linux Only)

## Requirements

- Electron
- Electron Packager
- Electron Debian Installer

```bash

# Install Electrom
sudo npm install -g electron --unsafe-perm=true

# installer debian package
sudo npm install -g electron-installer-debian

# Install Electron Packager
sudo npm install electron-packager -g

```

## Installation

- Clone this Respo

```bash
https://github.com/mskian/electron-example.git
```

- Install dependencies

```bash
cd electron-example
```

```bash
yarn
```

- Build a Package for Linux

```bash
yarn package-linux
```

- Build `.deb` Package

```bash
yarn create-debian-installer
```

## Customization

### Add ICONS

- Add Icons on `assets/icons` Directory
- open `https://appiconmaker.co` and Upload your ICON.Format `png` & size 512x512
- After Generating the ICONS download iOS icons zip file & Extract all the icons in `assets/icons` (PS: Before Adding your Own ICONS Cleanup Default icons which already added for example APP)
- Don't Rename the ICONS

### Convert the website/blog to Desktop APP

- open `main.js` File
- Find the Below & Update your Blog/website URL

```js
var weburl = 'https://status.santhoshveer.com';
```

- Add Background Color Find this Line `backgroundColor: '#15171A',` & Replace it with your Background Color code
- Test your APP

```bash
electron main.js
```

#### Deb package Setup

- `debian.json` = `dest` - Set the location for `.deb` package Storage After the Package Build
- `package.json` - Open it & replace it with your Name, Description and Version

```json
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "package-linux": "electron-packager .  electron-example --overwrite --platform=linux --arch=x64 --icon=assets/icons/Icon-1024.png --asar --prune=true --out=release-builds",
    "create-debian-installer": "electron-installer-debian --src release-builds/electron-example-linux-x64/ --arch amd64 --config debian.json"
  }
```

- `electron-example` - Replace with your APP Name
- `release-builds/electron-example-linux-x64/` - same Replace `electron-example` with your APP Name

### Learn More about Electron

Special thanks to Christian Engvall for this Awesome Tutorials

| # | Topic | Description |
|---|:------|-------------|
| 01 | [Hello world tutorial](http://www.christianengvall.se/electron-hello-world/) | Get electron running on your computer |
| 02 | [Testing electron app on Ubuntu](http://www.christianengvall.se/testing-electron-app-on-ubuntu-linux/) | Set up a VirtualBox virtual machine running Ubuntu and share app |
| 03 | [Electron app icons](http://www.christianengvall.se/electron-app-icons/) | Adding icons to the app |
| 04 | [Electron packager tutorial](http://www.christianengvall.se/electron-packager-tutorial/) | Creating packages for mac, windows and linux |
| 05 | [Electron menu](http://www.christianengvall.se/electron-menu/) | Adding a main menu to your Electron app |
| 06 | [Electron asar](http://www.christianengvall.se/electron-asar/) | Packaging the app with asar |
| 07 | [DMG Installer](http://www.christianengvall.se/dmg-installer-electron-app/) | Creating a DMG-installer for macOS |
| 08 | [Windows installer](http://www.christianengvall.se/electron-windows-installer/) | Creating a windows installer with electron-winstaller |
| 09 | [Debian package installer](https://www.christianengvall.se/electron-installer-debian-package/) | Create a debian package |
| 10 | [Update to latest Electron version](https://www.christianengvall.se/update-to-latest-electron-version/) | Update electron to the latest version using npm |

## LICENSE

MIT
