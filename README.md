eucalyptus-configureDNS
=======================

Role to configure Eucalyptus DNS properties

Requirements
------------

RTFM

Role Variables
--------------

| Name | Required | Default | Description
|--- |--- |--- |---
| enabled | yes | true | Defines if Eucalyptus DNS system is On of Off
| dnsdomain | yes | localhost | Defines the FQDN used by instances for the cloud systems
| nameserver | yes | nshost.localhost | Defines the DNS server FQDN used by Eucalyptus CLC
| nameserveraddress | yes | 127.0.0.1 | Defines the DNS server IP used by Eucalyptus
| use_dns_delegation | yes | false | Boolean to define if Eucalyptus will use delegation DNS system
| use_instance_dns | yes | false | Boolean to define if Eucalyptus instances should have a DNS name using the FQDN
| dns_listener_address_match | yes | empty string | String() of IP addresses separated with a comma the server will use to receive DNS quries
| loadbalancer_dns_subdomain | yes | lb | Defines the zubzone used for ELB FQDN. Can only be a single subnzone definition
| instance_subdomain | yes | .eucalyptus | Defines the default subdomain for instances names


Dependencies
------------

- JohnPreston.eucalyptus-getCredentials

- JohnPreston.eucalyptus-setVars

Example Playbook
----------------

```

- hosts: clc
  roles:
  - JohnPreston.eucalyptus-configureDNS
  vars:
  - dnsdomain: cloud.my-company.net
  - nameserver: ns1.cloud.my-company.net
  - nameserveraddress: 1.2.3.4
  - use_instance_dns: true

```

```

- hosts: clc
  roles:
  - JohnPreston.eucalyptus-configureDNS
  vars_files:
  - vars/dns_config.yml

```



License
-------

None

Author Information
------------------

John Preston [John Mille]


