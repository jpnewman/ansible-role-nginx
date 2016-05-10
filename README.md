# jpnewman.nginx


This ansible role configures nginx proxy.

## Requirements

- Ansible 2.x

## Role Variables

|Variable|Description|Default|
|---|---|---|
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
