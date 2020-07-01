# OpenSUSE Server

## Home Assistant 

```sh
ansible-playbook -i inventory/hosts.ini holly-homeassistant.yml -K --user $USER
```

Setup `group_vars/holly.yaml` by downloading

```sh
aws s3 cp s3://home-configuration-configurationbucket-13wmfldf19xzw/holly.yaml group_vars/holly.yaml
```

The following custom components exist in the home-assistant role's files folder. 

These are copied from
* https://github.com/custom-components/alexa_media_player
* https://github.com/segalion/securitasdirect
* https://github.com/zha-ng/zha-map
* https://github.com/Nimmsis/roon-hass

Custom lovelace card downloaded from
* https://github.com/dmulcahey/zha-network-visualization-card

Should the upstream repos be updated, the local copies can be updated by running:

```sh
ansible-playbook update-homeassistant-custom-components.yaml
```

## Minimserver

New music should be added to the files in `roles/music/files`

```sh
ansible-playbook -i inventory/hosts.ini holly-minim.yml -K --user $USER
```

## Samba

This is mostly copied from https://github.com/pwntr/samba-alpine-docker

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

# Octocam

```sh
ansible-playbook -i inventory/hosts.ini octocam.yml -K --user $USER
```