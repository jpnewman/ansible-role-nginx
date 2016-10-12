# jpnewman.nginx

[![Ansible Role](https://img.shields.io/ansible/role/9597.svg?maxAge=2592000)](https://galaxy.ansible.com/jpnewman/nginx/)
[![Build Status](https://travis-ci.org/jpnewman/ansible-role-nginx.svg?branch=master)](https://travis-ci.org/jpnewman/ansible-role-nginx)

This ansible role configures nginx proxy.

## Requirements

- Ansible 2.x

## Role Variables

### geerlingguy.nginx

|Variable|Description|Default|
|---|---|---|
|```nginx_vhosts```|For this wrapper role keep this as is.|[]|
|```nginx_remove_default_vhost```|For this wrapper role keep this as is.|true|

### jpnewman.nginx | defaults
|Variable|Description|Default|
|---|---|---|
|```nginx_vhost_available_path```||/etc/nginx/sites-available|
|```nginx_vhost_path```||/etc/nginx/sites-enabled|

### jpnewman.nginx | Simple Reverse Proxy Template (nginx_reverse_proxy.conf.j2)

|Variable|Description|Default|
|---|---|---|
|```nginx_vhost_filename```||localhost|
|```www_redirect```||false|
|```listen_ports```||80|
|```host_aliases```||[]|
|```max_upload_size```||"1024m"|
|```host_name```||localhost|
|```redirect_http```||false|
|```ssl_enabled```||false|
|```ssl_listen_ports```||[]|
|```ssl_cert_path```||""|
|```ssl_key_path```||""|
|```proxy_pass_port```||8080|
|```server_auth_method```||""|
|```nginx_log_dir```||"/var/log/nginx"|
|```nginx_error_log```||```"{{ nginx_log_dir }}/error.log"```|
|```nginx_access_log```||```"{{ nginx_log_dir }}/access.log"```|
|```nginx_template_file```||nginx_reverse_proxy.conf.j2|

### jpnewman.nginx | Multiple vhost template

|Variable|Description|Default|
|---|---|---|
|```nginx_vhosts_data```|||
|```nginx_acl_rules```|||

For examples see the following files, within this role: -

- ```test\templates\defaults\artifactory.yml```
- ```test\templates\defaults\drupal.yml```
- ```test\templates\defaults\kibana_reverse_proxy.yml```
- ```test\templates\defaults\multiple_vhosts.yml```

## Custom templates

Any custom template can be used via variable ```nginx_template_file``` and the needed variables placed in ```host_vars``` and ```group_vars```, etc.

## Dependencies

- geerlingguy.nginx

## Example Playbook

    - hosts: servers
      roles:
         - { role: jpnewman.nginx, tags: ["nginx"] }

## License

MIT / BSD

## Author Information

John Paul Newman
