# Home Lab

A collection of playbooks that setups and runs docker container within a swarm.

## Notes

- This playbook assumes this is being run on a debian based distro.
- On the nas docker needs to be installed on the interface

## Installing the requirements

```bash
ansible-galaxy install -r requirements.yml
```

## Testing the playbook

Testing of the playbook is done by [Vagrant](https://vagrantup.com). Just run
the following command in the terminal and 3 machines should start up to run the
playbook.

```bash
# To start the virtual machines
vagrant up

# Running the playbook
ansible-playbook -i inventory.vagrant setup.yml

# To stop the virtaul machines
vagrant destory
```
