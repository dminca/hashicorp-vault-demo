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

#### Useful resources
> These are nice-to-haves
- [Managing secrets with Vault + Consul](https://testdriven.io/blog/managing-secrets-with-vault-and-consul/)
- [Consul + Vault configuration](http://pcarion.com/2017/04/30/A-consul-a-vault-and-a-docker-walk-into-a-bar..html)
- [Docker + Consul + Vault: A Practical Guide](https://www.marcolancini.it/2017/blog-vault/)
- [Vault configuration](https://www.vaultproject.io/docs/configuration/ui/index.html)
