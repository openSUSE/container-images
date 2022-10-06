# Samba ADDC container

- [Guide](#guide)
  - [Run a new Samba ADDC instance](#run-a-new-samba-addc-instance)
  - [Options](#options)
  - [Environment variables](#environment-variables)

## Guide

### Run a new Samba ADDC instance

The command to run this container is:

```sh
podman run -d --rm --name samba-ad-dc registry.opensuse.org/opensuse/samba-ad-dc
```

### Options:
```
 -d <domain_name:type:admin:password>
    Configure an Active Directory domain controller in an existing domain.
     * domain_name      Required, domain name of the new/joining domain
     * type             Required, DC or RODC
     * admin            Required, the domain Administrator
     * password         Required, the Administrator password
 -p <domain_name:password>[:function_level:rfc2307]
    Provision a new Active Directory domain.
     * domain_name      Required, domain name of the new/joining domain
     * password         Required, the Administrator password
     * function_level   Optional, [2000|2003|2008|2008_R2] Domain and forest function level, default is 2008_R2
     * rfc2307          Optional, [yes|no] Use AD to store posix attributes (default = no)
 -h
    Display help text and exit
```
### Environment variables:
```
  DEBUG=[0|1]           Enable debug mode
  TZ=<timezone>         Set timezone
```
