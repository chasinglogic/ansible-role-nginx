Ansible role: nginx
==================================

Install and deploy NGINX configurations, simply. Works for RHEL and Ubuntu
systems.

Role Variables
--------------

| Name           | Description                                                                       | Type      | Default   | Required   |
| -------------- | --------------------------------------------------------------------------------- | :-------: | :-------: | :--------: |
| nginx_user     | User for running nginx. This is the non-root user that will be set in nginx.conf  | string    | www-data  | no         |
| vhosts         | List of virtual host domains, used to deploy configurations                       | string[]  | []        | no         |


### Deploying configurations

The variable `vhosts` is a list of domain names. These domains will be looked
for in the template directory so that `templates/{{ domain }}.conf` will be
deployed to `/etc/nginx/conf.d` which is loaded by the default nginx.conf
deployed with this role.

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: chasinglogic.nginx
```
