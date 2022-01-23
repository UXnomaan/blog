---
template: BlogPost
path: /mac-setup
date: 2021-03-04T03:26:08.444Z
title: "Setup your Mac in one command "
summary: You just got a new Mac or your old mac died, you could install all your apps one by one or use Homebrew to automate the process
thumbnail: ./static/img/Mac Setup.png
tags:
  - macOS
  - automation
---

If you have more than one laptop or get unlucky like me and end up with a dead MacBook, you dread spending hours to get all of your apps back. There is an easy way to setup all the apps on your mac. Other than TimeMachine of course.

I rely on [Homebrew](https://brew.sh) to install any software I need. This has several benefits, you do not need to click next or go through a GUI to install a package, and most importantly, when you have one computer fully setup, you can install the same packages easily on other machines and get it up and running in a matter of minutes. Even if you do not use brew to install your software, [mas](https://github.com/mas-cli/mas) (Mac App Store) integration, can record what you have installed through the AppStore and help you install those on a new laptop.

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
