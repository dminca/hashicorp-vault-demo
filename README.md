# HashiCorp Vault
> Used mainly for demo purposes and include HashiCorp Vault configuration
for LDAP

## Required steps
- configure LDAP auth backend on Vault
- make sure Consul is running with Vault
- login via LDAP
- configure credentials sharing per user

### LDAP configuration on Vault
- URL: ldaps://ldap.example.io
- use anonymous bind to discover the bind DN of a user
- prevent users from bypassing auth when providing entry pass

- CA certificate file: (optional)
- User Attribute: uid

- Customize User search:
  - User DN: `ou=users,dc=example,dc=io`

- Customize Group Membership search
  - Group Filter: `(&(ObjectClass=posixGroup))`
  - Group Attribute: `cn`
  - Group DN: `ou=groups,dc=example,dc=io`

