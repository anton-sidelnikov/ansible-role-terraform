[![Build Status](https://travis-ci.org/anton-sidelnikov/ansible-role-terraform.svg?branch=master)](https://travis-ci.org/anton-sidelnikov/ansible-role-terraform)

Inspired by: https://github.com/darkwizard242/ansible-role-terraform

# Ansible Role: Terraform

Role to install (_by default_) `terraform` package on **Debian/Ubuntu** and **EL** systems.
## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
terraform_app: terraform
terraform_osarch: linux_amd64
terraform_dl_url: https://releases.hashicorp.com
terraform_dl_loc: /tmp
terraform_bin_path: /usr/local/bin
```
If `terraform_version` not set then latest version will downloaded.

### Variables table:

Variable           | Value (default)                  | Description
------------------ | -------------------------------- | -----------------------------------------------------------------------------------------------------------------------------------------------------------
terraform_app      | terraform                        | Defines the app to install i.e. **terraform**
terraform_osarch   | linux_amd64                      | Defines os architecture. Used for obtaining the correct type of binaries based on OS System Architecture. Defaults to: **linux_amd64**
terraform_dl_url   | <https://releases.hashicorp.com> | Defines URL to download the terraform binary from.
terraform_dl_loc   | /tmp                             | Defined to dynamically set where to place the binary archive for `terraform` temporarily. Defaults to: **/tmp**
terraform_bin_path | /usr/local/bin                   | Defined to dynamically set the appropriate path to store terraform binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
 
## Example Playbook

For default behaviour of role (i.e. installation of **terraform**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - role: anton-sidelnikov.terraform
```