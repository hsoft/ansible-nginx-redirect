# nginx-redirect

Creates redirect directives in nginx config.

Supports SSL [acme-nginx][acme-nginx]-style. If the redirect is SSL-enabled, we need an nginx
snippet that is properly named and that contains ssl cert config, allowing us to properly redirect
SSL traffic.

## Requirements

* Ansible 2.0+
* Debian jessie target
* nginx being already installed (we don't do that in this role)

## Example

```
- hosts: all
  roles:
    - role: nginx-redirect
      nginx_redirects:
        - from: example.com
          to: www.example.com
          ssl: yes
```

See [defaults](defaults/main.yml) for more details.

[acme-nginx]: https://github.com/hsoft/ansible-acme-nginx
