---
template: BlogPost
path: /mac-setup
date: 2021-03-04T03:26:08.444Z
title: 'Setup your Mac in one command '
thumbnail: /assets/Mac Setup.png
---
If you have more than one laptop or unlucky like me and end up having your laptop have issues, you want to make sure setting up your laptop doesn't take a lot of time. 

I rely on [Homebrew](https://brew.sh) to install any software I need. This has several benefits, you do not need to click next or go through a GUI to install a package, and most importantly, when you have one computer fully setup, you can install the same packages easily on other machines and get it up and running in a matter of minutes. Even if you do not use brew to install your software, `mas` (Mac App Store) [https://github.com/mas-cli/mas] integration, can record what you have installed through the AppStore and help you install those on a new laptop. 

If you don't have brew installed: 

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
After it's installed. Run the following command to get a list of installed software: 

```
brew bundle dump --describe
```

This will create a Brewfile in the directory that it's run. `--describe` flag will add a comment to each package as to what the package is for; This helps if you don't recognize some of the names. 

Here's my [Brewfile](https://github.com/UXnomaan/mac-setup/blob/master/Brewfile).

After you have the file, move it to the computer you are trying to setup. This can be through iClould or physical USB drives. 

On the new computer, after installing `brew`, run this: 

```
brew bundle
```
