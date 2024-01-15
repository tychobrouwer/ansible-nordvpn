Install and configure NordVPN
=========

A brief description of the role goes here.

Role Variables
--------------

The ```nordvpn_username``` needs to be set to your NordVPN service username and ```nordvpn_password``` needs to be set to your NordVPN service password.

The ```nordvpn_server``` variable can be set to the NordVPN server you want to connect to. A list of servers can be found at <https://nordvpn.com/ovpn/>

```nordvpn_no_redirect_gateway``` can be set to ```false``` if you want to redirect all traffic through the VPN.

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
        - { role: tychobrouwer.nordvpn, nordvpn_username: service_username, nordvpn_password: service_password,
            nordvpn_server: us10036.nordvpn.com.udp1194 }
        - { role: tychobrouwer.nordvpn, nordvpn_username: service_username, nordvpn_password: service_password,
            nordvpn_server: us10036.nordvpn.com.udp1194, nordvpn_no_redirect_gateway: true }
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
