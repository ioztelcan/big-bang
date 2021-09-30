# big-bang

An ansible playbook for the first time setup of development machines.

## Summary

This is an ansible playbook that I use personally to speed up the setup of any new computer with Linux (preferably an Ubuntu flavor) to be used for development. The idea is to get a few requirements for this playbook installed, then run this to automate the installation of some apps and overall setup of the device.

## Requirements

There are a few steps to be taken before this script can be ran.

1. Install git

- Install git using your favorite method. I usually use the apt repos which tend to be a bit outdated but does the trick. Make sure your version is higher than `2.20`. Git will be required in the first step of the big bang to clone the dotfiles.

`sudo apt install git-all`

2. Install pip

- Assuming you are on a new enough distribution, everything python related will be using python3. Same goes for pip (i.e pip3). A nifty way of getting the latest version is:

```
wget https://bootstrap.pypa.io/get-pip.py
python get-pip.py --user
```

3. Install ansible

- As it is the main tool required to run the playbook, install ansible.

`pip3 install --user ansible`

## Usage

Big bang playbook is used in two steps with the `run` script. After first step it is important to either source all the changed environment variables and startup scripts again or simply start a new shell instance and toss the old one. To indicate which step you want, pass the number `1` or `2` to run script.

1. `./run 1`
2. Wait for ansible to do it's thing, everything is logged in big_bang.log as well in case something goes wrong.
3. Start a new shell process, same directory.
4. `./run 2`
5. Wait some more.
6. Profit.

## License

MIT, see LICENSE file for deets.