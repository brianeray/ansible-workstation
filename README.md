# ansible-workstation
Bootstrap some tooling and configuration for my client boxes. Also special playbooks for upgrading already-configured boxes: `pre-dist-upgrade.yml` and `post-dist-upgrade.yml`.

## Cheats
```bash
# First confirm that your primary user, group, and home dir is configured. This
# currently has placeholder values so as not to commit them to the repo.
git diff --ignore-all-space \
  --color-moved \
  --color-moved-ws=ignore-all-space \
  -- group_vars/all

# Confirming host facts
ansible localhost --module-name ansible.builtin.setup

# Running the playbook that sets up host from scratch. Throw in --check option
# for dry run mode.
sudo ansible-playbook --ask-become-pass \
  --inventory hosts.yml \
  --diff \
  -v \
  site.yml

# Linting the repo
ansible-lint
```
