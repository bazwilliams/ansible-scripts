# OpenSUSE Server

## Home Assistant 

```sh
ansible-playbook -i inventory/hosts.ini holly-homeassistant.yml -K --user $USER
```

Setup `group_vars/holly.yaml` with the following configuration

```yaml
---
homeassistant:
  latitude: ${lat}
  longitude: ${long}
  elevation: ${elevation}

darksky:
  api_key: ${api_key}

homeconnect:
  client_id:  ${client_id}
  client_secret:  ${client_secret}

alexa:
  username: ${email}
  password: ${password}
  region: amazon.co.uk

ring:
  username: YOUR_USERNAME
  password: YOUR_PASSWORD

alarm:
  code: HA_ALARM_CODE

verisure:
  username: ${username}
  password: ${password}

opnsense:
  url: ${opnsense.url}
  api_secret: ${opnsense.api_secret}
  api_key: ${opnsense.api_key}
  tracker_interfaces:
    - LAN
```

The following custom components for homeconnect exist in the home-assistant role's files folder. 

These are copied from
* https://github.com/DavidMStraub/homeassistant-homeconnect 
* https://github.com/custom-components/alexa_media_player
* https://github.com/segalion/securitasdirect
* https://github.com/4n0nD3v3l0p3r/Home_Assistant_SkyQ_MediaPlayer
* https://github.com/zha-ng/zha-map

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