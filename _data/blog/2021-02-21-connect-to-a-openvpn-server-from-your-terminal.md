---
template: BlogPost
path: /connect-to-openvpn-from-terminal
date: 2021-02-20T23:51:19.486Z
title: 'Connect to a OpenVPN server from your terminal '
thumbnail: /assets/Group 3.png
---
OpenVPN is a free VPN protocol that you may use for work or home (PiVPN). The GUI is okay but I don't like to have any space taken on the Menu bar or the dock for a simple tool like OpenVPN. Because of that, I looked into running it from the command line.  Install OpenVPN: 

```shell
brew install openvpn
```

This installs the OpenVPN binary but for some reason is not add to your PATH.  Add the following to your `.zshrc` or `.bashrc` (source) : 

```shell
export PATH=$(brew --prefix openvpn)/sbin:$PATH
```

Make sure you close your terminal or source your .zshrc. Verify OpenVPN is now in your path: 

```shell
openvpn --version
```

At this point, add an alias to your `.zshrc` to connect to the VPN - there are better and more sophisticated approaches to this but not the topic of this writeup. 

## Prompt for username and password:
```shell
alias vpn="sudo openvpn --config /Users/nomaan/Documents/config.ovpn --daemon work-vpn"
```

This will start the VPN process as a daemon so you can close the terminal at this point.  

## Skip username and password 
If you want to skip the username and password, (not recommended), you can use `--auth-user-pass` flag. Create a txt file with your username on the first line and your password on the second line. 

```shell
alias vpn="sudo openvpn --config /Users/nomaan/Documents/config.ovpn  --auth-user-pass /Users/nomaan/Documents/auth.txt --daemon work-vpn"
```

## Stop openvpn 
So far, we know how to start an openvpn connection, what if you need to stop it? You need to use `--writepid` flag to write the process id to a text file. Update your alias to include this flag: 

```shell 
alias vpn="sudo openvpn --config /Users/nomaan/Documents/config.ovpn  --auth-user-pass /Users/nomaan/Documents/auth.txt --daemon work-vpn --writepid /Users/nomaan/Documents/openvpn-pid.txt"
```

If you run this alias now, `openvpn-pid` will be created with the process id. 
Add a new alias now to read the file and kill the process. 

```shell 
alias nvpn="sudo kill -9 $(less vpn-pid.txt)"
```

