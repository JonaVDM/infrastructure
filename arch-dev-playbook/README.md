# Arch Dev Playbook

A ansible playbook to setup a fresh arch based workstation.

## Running the playbook

In order to run this you need to change the `default.config.yml` to the values
you want, next you want to make sure that you have a version of python installed.

You need a local user that has access to sudo.

After you have done that you can simply run the following command:

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
sudo systemctl enable gdm
sudo systemctl enable greetd
```
