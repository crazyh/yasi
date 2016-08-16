yasi
====

yasi is yet another stupid installer for [Arch Linux](https://www.archlinux.org/) built on top of [Ansible](https://github.com/ansible/ansible) playbook.

It is based on boring Arch Linux [installation guide](https://wiki.archlinux.org/index.php/installation_guide) and allows to get a minimal bootable ready-to-use Arch Linux installation in several minutes.

Usage
-----

### Remote scenario

- Install Ansible locally
- Download, burn and boot Arch Linux somewhere, enable SSH and get IP address
- Run `ansible-playbook -i <ip-address>, site.yml` locally, answer questions and be patient

### Local scenario

TODO: add local installation scenario

### Supported options

Options can be passed to ansible-playbook via `-e option=value` or `-e @path/to/option/file` to supress prompts. See `man ansible-playbook` for more details.

TODO: add description and usage notes for humans

- bootloader (default: auto)
- device (default: /dev/sda)
- filesystem (default: btrfs)
- firmware (default: auto)
- mirrorlist (default: https://www.archlinux.org/mirrorlist/all/)
- packages
- password (default: password)
- reboot (default: no)
- timezone (default: UTC)
- wipe (default: no)

This playbook is idempotent so you can stop and run the playbook again as many as you want but note that changing of initial options after the first run usually is a bad idea (use the same options every time, use `auto` or use `wipe=yes`).

### Examples

TODO

Tested
------

### Host

- Ansible 2.1.0.0
- Fedora 23
- Python 2.7.11

### Target

- [archlinux-2016.06.01-dual.iso](https://www.archlinux.org/releng/releases/2016.06.01/)
- [archlinux-2016.08.01-dual.iso](https://www.archlinux.org/releng/releases/2016.08.01/) (EFI)

Thanks
------

- [Judd Vinet](https://github.com/jvinet), [Aaron Griffin](https://www.archlinux.org/people/developers/#aaron) and [others](https://www.archlinux.org/people/developers/) for Arch Linux
- [Michael DeHaan](https://github.com/mpdehaan) and Ansible contributors for Ansible
