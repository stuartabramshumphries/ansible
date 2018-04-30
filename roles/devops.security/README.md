# Role Name: security

security for system init

## Requirements

None

## Role Variables

###  `defaults/main.yml`
*default lower priority variables for this role*

* `security_sudoers_user: 'ops'`
* `security_sudoers_password: '$6$rounds=656000$8ETOoi63TbQac4H2$OvCTTiT..TvQISBMuLKm6DbpHsFoGYRRRvG9m59JHW5ShysMwan.kMyBqIbnaSc2regp3NKRO062QaxcbDaUO0'`
    > SHA512 password

* `security_sudoers_user_key: ''`
* `security_sudoers_passwordless: false`
* `security_sudoers_passworded: true`

###  `vars/RedHat.yml`
*The variables for RedHat/CentOS*

## Dependencies

None

## Example Playbook

    - name: security configure
      hosts: servers
      vars:
        security_sudoers_user: 'ops'
        security_sudoers_password: '$6$rounds=656000$8ETOoi63TbQac4H2$OvCTTiT..TvQISBMuLKm6DbpHsFoGYRRRvG9m59JHW5ShysMwan.kMyBqIbnaSc2regp3NKRO062QaxcbDaUO0'
        security_sudoers_user_key: 'ssh-rsa ...'  # public key
      roles:
         - security

## License

MIT / BSD

## Author Information

z
