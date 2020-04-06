# Ansible Role: uberspace-web-domain

This is part of the uberspace roles collection.

This is meant to be used on your [Uberspace](https://uberspace.de/).

Please be aware, that I'm neither part of the Uberspace team, nor am I associated to them other than having some Uberspaces myself.
This project was created, because I wanted to use the roles for myself and thought they were okay-ish enough to share them.

## What is this (from the uberspace manual)

Every Uberspace account gets its own domain in the form of \$USER.uber.space. You can setup as many additional domains as you like.

You can find the documentation of the replaced tool `uberspace web domain` in the Uberspace Manual [here](https://manual.uberspace.de/web-domains.html).

## Usage

| Variable | Choices/Default                            | Description                                                             |
| :------: | :----------------------------------------- | :---------------------------------------------------------------------- |
|  domain  |                                            | The domain you want to recieve requests on                              |
|  state   | <ul><li>present ✔</li><li>absent</li></ul> | "present" to be able to recieve requests, "absent" to remove the domain |
| domains  | []                                         | A list of domain, state combinations to set multiple domains at once    |

## Examples

### Add Domain

```yaml
- hosts: uberspace
  roles:
    - name: uberspace-web-domain
      domain: isabell.example
```

### Remove Domain

```yaml
- hosts: uberspace
  roles:
    - name: uberspace-web-catchall
      domain: isabell.example
      state: absent
```

### Set multiple Domains

```yaml
- hosts: uberspace
  roles:
    - name: uberspace-web-domain
      domains:
        - domain: present.isabell.example
        - domain: absent.isabell.example
          state: absent
```
