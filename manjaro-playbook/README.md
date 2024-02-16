# Manjaro Dev Playbook

A ansible playbook to setup a fresh manjaro based workstation. This is a
simpler version of the arch dev playbook.

## Installing the requirements

```bash
ansible-galaxy install -r requirements.yml
```

## Running the playbook

After setting the right variables in de config files, run the following command.

```bash
ansible-playbook -i inventory main.yml -u [insert_username] --ask-become-pass
```

Note: Ansible for some odd reason did not have the `ansible_user` when the -u
(uesr) parameter was not present.

## After running the play

There seems to be a bug of some sorts in the service module. Where the play
would crash whenever you try to enable a service which already enable.

So for now this has to be done after the run.

```bash
sudo systemctl enable wol@[interface]
```

Also not a bad idea to restart the machine.

## Complete script

```bash
sudo pacman -S ansible
mkdir ~/Code
git clone https://github.com/JonaVDM/infrastructure.git ~/Code/infrastructure
ansible-galaxy install -r requirements.yml
ansible-playbook -i inventory main.yml -u jona --ask-become-pass
```

## Extensions

Did not have time yet to really put in extensions with a method i like. So for 
now here is a list of extensions and settings on my install:

- https://extensions.gnome.org/extension/3193/blur-my-shell/
- https://extensions.gnome.org/extension/4442/gsnap/
- https://extensions.gnome.org/extension/1460/vitals/
- enable launch new instance

keybindings:

- (gnome tweaks) remap caps -> escape
- Super + E -> Open files (cmd: nautilus)
- Super + Return (enter) -> Open terminal
- Super + F -> Toggle fullscreen mode

Settings:
- Mouse acceleration: off
- Accessibility -> typing -> repeat keys, slighty faseter.
- Search:
    - files
    - calculator
    - settings
- multitasking
    - enable workspaces on all displays
    - app switching: current only
