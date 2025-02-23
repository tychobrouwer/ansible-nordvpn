Install and configure NordVPN
=========

A brief description of the role goes here.

Role Variables
--------------

The ```nordvpn_username``` needs to be set to your NordVPN service username and ```nordvpn_password``` needs to be set to your NordVPN service password.

The ```nordvpn_server``` variable can be set to the NordVPN server you want to connect to. A list of servers can be found at <https://nordvpn.com/ovpn/>

```nordvpn_ignore_redirect_gateway``` can be set to ```false``` if you want to redirect all traffic through the VPN.

```nordvpn_route_nopull``` can be set to ```false``` if you want to use the VPN as the default gateway.

```nordvpn_additional_route_addresses``` can be set to a list of addresses that need to be routed through the VPN.

```nordvpn_additional_route_ips``` can be set to a list of IP addresses that need to be routed through the VPN.

Example Playbook
----------------

```yaml
- hosts: servers
  vars:
    nordvpn_additional_route_addresses:
      - https://networkcalc.com/api/dns/lookup/skyhook.sonarr.tv
      - https://networkcalc.com/api/dns/lookup/apt.sonarr.tv
    nordvpn_additional_route_ips:
      - "1.1.1.1"

    nordvpn_username: service_username
    nordvpn_password: service_password
    nordvpn_server: us10036.nordvpn.com.udp1194

  roles:
    - role: tychobrouwer.nordvpn

    - role: tychobrouwer.nordvpn
      nordvpn_ignore_redirect_gateway: true
      nordvpn_route_nopull: false
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
