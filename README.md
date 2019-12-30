# OpenSUSE Server

```sh
ansible-playbook -i inventory/hosts.ini holly.yml -K --user $USER
```

Setup `group_vars/holly.yaml` with the following configuration

```yaml
---
homeassistant:
  darksky_api_key: ${api_key}
```

There is a custom component for homeconnect in the home-assistant role's files folder. This is copied from https://github.com/DavidMStraub/homeassistant-homeconnect Should the upstream repo be updated, the local copy can also be updated by running:

```sh
ansible-playbook update-homeassistant-homeconnect.yaml
```

Equally, the `homeassistant-homeconnect-update` role could also be added to the playbook... 

# Lightsail

Setup `group_vars/lightsail.yaml` with the following configuration

```yaml
---
owncloud:
  http_port: 8080
  domain: localhost
  admin_user: admin
  admin_password: ${owncloud_password}
irc:
  freenode:
    nick: ${irc_nick}
    username: ${freenode_username}
    password: ${freenode_password}
```

```sh
ansible-playbook -i inventory/hosts.ini lightsail.yml -K --user $USER
```