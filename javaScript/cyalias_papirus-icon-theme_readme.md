 
   
 

 
   
   
   
   
   
 

Papirus is a free and open source SVG icon theme for Linux, based on [Paper Icon Set](https://github.com/snwh/paper-icon-theme) with a lot of new icons and a few extras, like [Hardcode-Tray support](#hardcoded-tray-icons), [KDE colorscheme support](#kde-colorscheme), [Folder Color support](#folders-color), and [others](#extras).

Papirus icon theme is available in four variants:

 - Papirus
 - Papirus Dark
 - Papirus Light
 - ePapirus (for elementary OS and Pantheon Desktop)

## Contents

 - [Installation](#installation)
    - [Ubuntu and derivatives](#ubuntu-and-derivatives)
    - [Debian and derivatives](#debian-and-derivatives)
    - [Papirus Installer](#papirus-installer)
    - [Third-party packages](#third-party-packages)
 - [Hardcoded icons](#hardcoded-icons)
    - [Hardcoded application icons](#hardcoded-application-icons)
    - [Hardcoded tray icons](#hardcoded-tray-icons)
 - [KDE colorscheme](#kde-colorscheme)
 - [Folder's color](#folders-color)
 - [Extras](#extras)
 - [Recommendations](#recommendations)
 - [Manual fixes](#manual-fixes)
 - [Icon request](#icon-request)
 - [Contributing](#contributing)
 - [Donate](#donate)
 - [License](#license)

## Installation

### Ubuntu and derivatives

You can install Papirus from our official [PPA](https://launchpad.net/~papirus/+archive/ubuntu/papirus):

```
sudo add-apt-repository ppa:papirus/papirus
sudo apt-get update
sudo apt-get install papirus-icon-theme
```

or download .deb packages from [here](https://launchpad.net/~papirus/+archive/ubuntu/papirus/+packages?field.name_filter=papirus-icon-theme).

**NOTE:** Now the daily builds of the papirus-icon-themes package are placed in [`ppa:papirus/papirus-dev`](https://launchpad.net/~papirus/+archive/ubuntu/papirus-dev).

### Debian and derivatives

Debian users also can install Papirus from our [PPA](https://launchpad.net/~papirus/+archive/ubuntu/papirus), but the commands will differ:

```
sudo sh -c "echo 'deb http://ppa.launchpad.net/papirus/papirus/ubuntu bionic main' > /etc/apt/sources.list.d/papirus-ppa.list"

sudo apt-get install dirmngr
sudo apt-key adv --recv-keys --keyserver keyserver.ubuntu.com E58A9D36647CAE7F
sudo apt-get update
sudo apt-get install papirus-icon-theme
```

### Papirus Installer

Use the scripts to install the latest version directly from this repo (independently of your distro):

**NOTE:** Use the same script to update icon themes.

#### ROOT directory (recommended)

```
wget -qO- https://git.io/papirus-icon-theme-install | sh
```

#### HOME directory for GTK

```
wget -qO- https://git.io/papirus-icon-theme-install | DESTDIR="$HOME/.icons" sh
```

#### HOME directory for KDE

```
wget -qO- https://git.io/papirus-icon-theme-install | DESTDIR="$HOME/.local/share/icons" sh
```

#### \*BSD systems

```
wget -qO- https://git.io/papirus-icon-theme-install | env DESTDIR="/usr/local/share/icons" sh
```

#### Uninstall

```
wget -qO- https://git.io/papirus-icon-theme-uninstall | sh
```

### Third-party packages

Packages listed in this section are third-party packages. If you have a problem or a question, please contact the package maintainer.

Please note that some packages in the list may be outdated, open [Repology](https://repology.org/project/papirus-icon-theme/versions) to find out package versions.

| **Distro**    | **Maintainer**       | **Package**                              |
| :------------ | :------------------- | :--------------------------------------- |
| ALT Linux     | Andrey Cherepanov    | `apt-get install papirus-icon-theme`  [[link](https://packages.altlinux.org/en/Sisyphus/srpms/papirus-icon-theme)]  |
| Arch Linux    | Felix Yan            | `sudo pacman -S papirus-icon-theme`  community  |
| Arch Linux    | Mohammadreza Abdollahzadeh | [papirus-icon-theme-git](https://aur.archlinux.org/packages/papirus-icon-theme-git/)  AUR  |
| Debian 9+     | Yangfl               | `sudo apt install papirus-icon-theme` |
| Fedora 27+    | Robert-André Mauchin | `sudo dnf install papirus-icon-theme` |
| Fedora        | Dirk Davidis         | [papirus-icon-theme](https://copr.fedorainfracloud.org/coprs/dirkdavidis/papirus-icon-theme/)  copr  |
| FreeBSD       | Hiroki Tagato        | [papirus-icon-theme](https://www.freshports.org/x11-themes/papirus-icon-theme)  freshports  |
| NetBSD        | Nia Alarie           | [papirus-icon-theme](http://pkgsrc.se/graphics/papirus-icon-theme)  pkgsrc  |
| NixOS         | Nixpkgs Contributors | `nix-env -iA nixos.papirus-icon-theme` |
| openSUSE      | Konstantin Voinov    | [papirus-icon-theme](https://software.opensuse.org/download.html?project=home:kill_it&package=papirus-icon-theme)  OBS [[link](https://build.opensuse.org/package/show/home:kill_it/papirus-icon-theme)]  |
| openSUSE      | Matthias Eliasson    | [papirus-icon-theme](https://software.opensuse.org/package/papirus-icon-theme)  official  |
| ROSA Linux    | Vladimir Penchikov   | `sudo urpmi papirus-icon-theme` |
| Solus         | Joshua Strobl        | `sudo eopkg it papirus-icon-theme` |
| Ubuntu 18.04+ | Yangfl               | `sudo apt install papirus-icon-theme` |
| Void Linux    | Giuseppe Fierro      | `sudo xbps-install -S papirus-icon-theme` |

**NOTE:** If you are a maintainer and want to be in the list, please create an issue or make a pull request.

## Hardcoded icons

Some software uses an absolute path instead of the icon name in a .desktop file or in the source code which makes them unthemable.

### Hardcoded application icons

To deal with hardcoded application icons we recommend using [hardcode-fixer](https://github.com/Foggalong/hardcode-fixer). Papirus supports most of the applications in the [list](https://github.com/Foggalong/hardcode-fixer/blob/master/tofix.csv). If [hardcode-fixer](https://github.com/Foggalong/hardcode-fixer) doesn't support your favorite app yet, please open an issue [here](https://github.com/Foggalong/hardcode-fixer/issues) or edit your .desktop file manually.

### Hardcoded tray icons

To fix hardcoded tray icons Papirus supports [Hardcode-Tray](https://github.com/bil-elmoussaoui/Hardcode-Tray) script. A list of supported applications is available [here](https://github.com/bil-elmoussaoui/Hardcode-Tray/tree/master/data/database).

**NOTE:** To get Papirus to work right with Hardcode-Tray, use the hardcode-tray option `--conversion-tool RSVGConvert`:

```
sudo -E hardcode-tray --conversion-tool RSVGConvert --size 22 --theme Papirus
```

**Size recommendations:**

- Unity 22px
- KDE 22px
- GNOME 22px ([see](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme#manual-fixes) for more info)
- XFCE 22px ([see](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme#manual-fixes) for more info)
- Pantheon 24px
- Cinnamon 16px


![hardcode-tray](https://i.imgur.com/6hFm6aj.png)

**NOTE**: Some Electron-based applications have blurred tray icon on KDE (see [bug report](https://bugs.kde.org/show_bug.cgi?id=366062)). To solve this issue pass the following environment variable to the app: `XDG_CURRENT_DESKTOP=Unity wire-desktop`

## KDE colorscheme

Support for monochrome icons for KDE colorscheme is now available:
- Papirus - for dark plasma theme & light color scheme
- Papirus Dark - for dark plasma theme & color scheme
- Papirus Light - for light plasma theme & color scheme

![kde-color-scheme](https://i.imgur.com/oM1qhQH.png)

**NOTE:** Non-KDE apps don't support KDE colorscheme on the system tray, but you can replace color manually.

## Folder's color

Papirus has [Folder Color](http://foldercolor.tuxfamily.org/) v0.0.80+ support that allows you to change a color of a folder.

Available colors:

![Folder Color Preview](https://i.imgur.com/jP3mRci.png)

For KDE, colors of individual folders can be changed using [dolphin-folder-color](https://github.com/audoban/dolphin-folder-color).

Also, you can use our [papirus-folders](https://github.com/PapirusDevelopmentTeam/papirus-folders) script to apply the color of folders system-wide.

## Extras

- [Papirus theme for LibreOffice](https://github.com/PapirusDevelopmentTeam/papirus-libreoffice-theme)
- [Papirus themes for FileZilla](https://github.com/PapirusDevelopmentTeam/papirus-filezilla-themes)
- [Papirus theme for SMPlayer](https://github.com/PapirusDevelopmentTeam/papirus-smplayer-theme)
- [Papirus themes for Claws Mail](https://github.com/PapirusDevelopmentTeam/papirus-claws-mail-theme)
- [Papirus themes for Thunderbird](https://github.com/PapirusDevelopmentTeam/thunderbird-theme-papirus)
- [Papirus theme for aMule](https://github.com/PapirusDevelopmentTeam/papirus-amule-theme)

## Recommendations

- Recommended use Papirus icons alongside one of the following GTK themes:
  - [Adapta theme](https://github.com/adapta-project/adapta-gtk-theme)
  - [Arc theme](https://github.com/NicoHood/arc-theme)
  - [Materia theme](https://github.com/nana-4/materia-theme)
- For KDE, our recommendation is:
  - [Adapta KDE](https://github.com/PapirusDevelopmentTeam/adapta-kde)
  - [Arc KDE](https://github.com/PapirusDevelopmentTeam/arc-kde)
  - [Materia KDE](https://github.com/PapirusDevelopmentTeam/materia-kde)

## Manual fixes

 
 For Cinnamon users 

For Cinnamon users who want to use Papirus icon theme with [Arc theme](https://github.com/NicoHood/arc-theme) we recommend fix color icons on panel:

```
sudo sed -i.orig 's/white/#d3dae3/g' /usr/share/themes/Arc-Dark/cinnamon/cinnamon.css
```

![Cinnamon Arc-Dark theme fix](https://i.imgur.com/XXejgtD.png)

To deal with blurred panel icons, increase the panel size up to 30px in `Systems Settings` → `Panel` (see [screenshot](https://i.imgur.com/oToRBYv.png)).
 

 
 For GNOME Shell users 

For GNOME users we recommend install the following extensions:

- [(K)StatusNotifierItem/AppIndicator Support](https://extensions.gnome.org/extension/615/appindicator-support/) **¹** — This extension integrates AppIndicators. The patched version of [sni-qt](https://github.com/bilelmoussaoui/sni-qt) for [Hardcode-Tray](https://github.com/bilelmoussaoui/Hardcode-Tray) doesn't work without it.
- [Dash to Dock](https://extensions.gnome.org/extension/307/dash-to-dock/) **¹**
- [No Symbolic Icons](https://extensions.gnome.org/extension/1304/no-symbolic-icons/)
- [Status Area Horizontal Spacing](https://extensions.gnome.org/extension/355/status-area-horizontal-spacing/)

**¹** On Ubuntu 18.04+ it is pre-installed.
 

 
 For Xfce users 

Here are a few recommendations for Xfce users.

#### Thunar File Manager

Go to `Edit` → `Preferences...`. Click on `Side Pane` tab. Under `Side Pane`, look for `Icon Size` and set to `Very Small`.

![thunar-prefecences](https://i.imgur.com/Iu1TIEa.png)

#### Notification Area

Go to `Settings Manager` → `Panel` → `Items` tab. Select `Notification Area` item and click on `Edit currently selected item` button. Under `Appearance` set the following options:

- Set `Maximum icon size (px)` to `24`
- Uncheck `Show frame`

![xfce4-notification-area](https://i.imgur.com/MopCZBZ.png)
 

 
 For elementary/Pantheon users 

With light wallpaper, we recommend disable `use-transparency` option on wingpanel:

```
gsettings set org.pantheon.desktop.wingpanel use-transparency false
```

 

## Icon request

- Application name
- Icon name (see desktop-file option **Icon** on `/usr/share/applications`)
- Original icon image
- Small description and/or a link to the official webpage

**NOTE**: We do NOT support Windows/Wine/Crossover or other NOT native Linux-apps. This also applies to discontinued projects!!

## Contributing

We welcome user contributions. If you don't know where to start, we've compiled a list of things we would like to see in your pull request:

- new icons for missing applications
- symbolic links to an existing icon
- resolving open issues
- spelling, grammar, phrasing
- improvements to our scripts

Inside [tools/work](tools/work) you will find a step-by-step guide, an environment, and tools that will help you:

- [create a new icon](tools/work#create-a-new-icon) from template
- [make a symlink to an existing icon](tools/work#make-symlinks-to-an-existing-icon)
- [edit an existing icon](tools/work#edit-an-existing-icon)
- convert your icon to all variants of the theme

We are waiting for your pull requests and would love to see this icon theme become as complete as possible.

## Donate

You can support this open source project by making a voluntary payment:

- Patreon: https://www.patreon.com/varlesh
- PayPal: https://www.paypal.me/varlesh

## License

Papirus icon theme distributed under the terms of the GNU General Public License, version 3. See the [`LICENSE`](LICENSE) file for details.


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)