Role Name
=========

This role implements RH Solutions [2026163](https://access.redhat.com/solutions/2026163) .


Requirements
------------

Satellite 6.2 host

Role Variables
--------------
```yaml
rhsm_squid_proxy_packages:
  - squid
  - libselinux-python
  - policycoreutils-python
rhsm_squid_proxy_service_name: squid2
rhsm_squid_proxy_conf_src: "squid2.conf.j2"
rhsm_squid_proxy_conf_dest: "/etc/squid/squid2.conf"
rhsm_squid_proxy_sysconfig_src: "squid2.j2"
rhsm_squid_proxy_sysconfig_dest: "/etc/sysconfig/squid2"
rhsm_squid_proxy_service_unit_src: "squid2.service.j2"
rhsm_squid_proxy_service_unit_dest: "/etc/systemd/system/squid2.service"
rhsm_squid_proxy_http_port: 4827
rhsm_squid_proxy_visible_hostname: "localhost-squid2"
rhsm_squid_proxy_dstdomain: "YOURDOMAIN"
rhsm_squid_proxy_localips:
  - "10.0.0.0/8"
  - "192.168.0.0/16"
rhsm_squid_proxy_external_proxy_ip: "192.168.1.1"
rhsm_squid_proxy_external_proxy_port: "1234"
```

Dependencies
------------

- libselinux-python
- policycoreutils-python

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: "yes"
      roles:
         - { role: rhsm-squid-proxy }

License
-------

BSD
