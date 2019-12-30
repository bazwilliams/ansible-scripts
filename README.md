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

The following custom components for homeconnect exist in the home-assistant role's files folder. 

These are copied from
* https://github.com/DavidMStraub/homeassistant-homeconnect 
* https://github.com/custom-components/alexa_media_player. 

Should the upstream repos be updated, the local copies can be updated by running:

```sh
ansible-playbook update-homeassistant-custom-components.yaml
```

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