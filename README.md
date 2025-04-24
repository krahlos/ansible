# Ansible playbooks

This repository contains a collection of `Ansible` playbooks for my needs.

## TL;DR

### Prerequisites

**Control machine**

* Python 3 (≥3.8)
* Ansible (≥2.10)

**Target hosts**

* Python 3 installed (Ansible’s default connector uses `/usr/bin/python3`)
* SSH access

### Installation

The instructions to install `Ansible` under `Ubuntu` can be found
[here](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu).

```shell
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

For `macOS` it can be installed via `brew`

```shell
brew install ansible
```

### Clone the repo

```shell
https://github.com/krahlos/ansible.krahlos.git
cd ansible.krahlos
```

### Review `inventory/hosts.ini`

By default it contains

```ini
[all]
localhost ansible_connection=local
```

To target remote servers replaye `localhost` with their hostnames or IPs.

### Validate the playbook

Before touching or destroying anything check the syntax

```shell
ansible-playbook site.yml --syntax-check
```

And because we are a little paranoid we do a dry-run

```shell
ansible-playbook site.yml --check --diff
```

### Run the playbook

Once we are happy with the outcome of the previous step we can run the playbook

```shell
ansible-playbook site.yml
```

## Sources

* [Installing and using Pre-commit with Ansible-lint](https://blog.42mate.com/installing-and-using-pre-commit-with-ansible-lint/)
