# Ansible ACE DO

These playbooks set up the lab for the accompanying introduction to Ansible talk found here: <link>.

NB: this is NOT the seed project to participate in the lab. That can be found here: <link>. (You also won't find any info on completing the lab here ;P).

## Requirements

These playbooks assume you have a Digital Ocean account as well as use CloudFlare to manage your DNS records (TODO: currently, no way to skip this without changing the playbooks).

You'll also need the Python module `dopy` installed on the Ansible host for the Digital Ocean modules to work.

## Installation

Modify `roles/droplet/vars/main.yml` to enumerate the boxes you want provisioned (TODO: pull this list into top-level variables).

Use `provision.yml` to set up the boxes and `cleanup.yml` to tear them down. You should be able to use plain `ansible-playbook provision.yml` without any options (the ansible.cfg should be configured for most setups).

You'll need to configure at least the following variables. The recommendation is to replace `vault.yml` with your own.

```yml
vault_cloudflare_token: <TOKEN>
vault_cloudflare_email: <email address>
vault_cloudflare_zone: <domain>

vault_user_pass: <user password>

vault_do_key_ids:
  - "<ID of key in DO>"
```
