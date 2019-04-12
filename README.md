# Electron Desktop APP for Linux

Convert your website to Desktop APP using Electron (Currently Build Package for Linux Only soon Available for Windows)

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

- Clone the Respo

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

#### Deb package Setup

- `debian.json` = `dest` - Set the location for `.deb` package Storage After the Package Build
- `package.json`

```json
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "package-linux": "electron-packager .  electron-example --overwrite --platform=linux --arch=x64 --icon=assets/icons/Icon-1024.png --asar --prune=true --out=release-builds",
    "create-debian-installer": "electron-installer-debian --src release-builds/electron-example-linux-x64/ --arch amd64 --config debian.json"
  }
```

- `electron-example` - Replace with your APP Name
- `release-builds/electron-example-linux-x64/` - same Replace `electron-example` with your APP Name

Learn More about Deb Package - <https://www.christianengvall.se/electron-installer-debian-package/>

## LICENSE

MIT
