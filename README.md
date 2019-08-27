
Clean-up uniqueMember entries in groupOfUniqueNames

Currently this script interactively asks what to do for every group.
There is no unattended mode yet.

## Development environment

### PipEnv

Install dependencies
```bash
pipenv install
```

Execute the script directly
```bash
pipenv run ./px-ldap-group-cleanup
```

or activate the venv-first
```bash
pipenv shell
./px-ldap-group-cleanup
```


### Pip

Install dependencies
```bash
pip install -r requirements-devel.txt
```

Dynamically linking to the repo
```bash
python3 setup.py develop
```


## Installation

Install dependencies
```bash
pip install -r requirements.txt
```

Statically install the script
```bash
python setup.py install
```


## Configuration

All parameters set via command-line can also be set in the config.

`~/.config/px-ldap-group-cleanup.yaml`:
```yaml
---
# the ldap-servers domain-name or IP
host: ldap.example.org
# where to start searches
search_base: dc=example,dc=org
# user-dn for bind
bind_dn: cn=my-script-user,ou=admins,dc=example,dc=org
# user password
bind_pw: <better-use-stdin>
...

```

## Example

If no password is is defined it will be requested via `getpass`:
```bash
px-ldap-group-cleanup \
  --host='ldap.example.org' \
  --search-base='dc=example,dc=org' \
  --bind-dn='cn=my-script-user,ou=admins,dc=example,dc=org'
```
