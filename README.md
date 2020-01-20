## ansible_DHCP
This role is used to install and configure a local Gitlab server.
- Firewall is configured
- Gitlab software is installed
- Configuration is done based on a template
- Variables 

## Requirements
This role is tested on RHEL and CentOS 7.7.
Gitlab version is latest.

## Role Variables
The following variables are used in the template.

git_external_url: "{{ ansible_fqdn }}"

The external URL used by the server

git_default_theme: 4

The default theme used by gitlab

git_email_display_name: "Gitlab"

Mail sender display name

git_email_enabled: !!str true

enable the email. Note the !!str. This is to force true. Will use boolean without !!str which will break the gitlab server.

git_time_zone: "UTC"

The timezone for the gitlab server

git_sidekiq_timeout: 5

The sidekiq timeout configured in Gitlab.


## Dependencies
None

## Example Playbook
  # YAML file for dhcp roles
  #
  # Keep this file as clean as possible! 
  #
  - hosts: ansible_gitlab
    become: true
    roles:
      - ansible_gitlab

License
-------

MIT

Author Information
------------------
Bernhard Muts
https://github.com/badmuts13/
