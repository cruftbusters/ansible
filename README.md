# Ansible control plane for Diamond

Baseline Ansible project for provisioning the Diamond server (192.168.90.49).

## Layout

- `ansible.cfg` — project config (inventory path, host key checking off for first contact)
- `inventory/hosts.ini` — inventory; host `diamond` (group `servers`) uses the `headscale` user and the key at `~/code/cruftbusters/diamond-ssh/headscale/id_ed25519`
- `site.yml` — no-op playbook (`ping` module) to verify connectivity

## Usage

```bash
cd ~/code/cruftbusters/ansible
ansible-playbook site.yml
```

## Notes

- SSH keys live outside this repo in `~/code/cruftbusters/diamond-ssh/` (0600). Never commit keys or passwords here.
- The `coolify` key (`~/code/cruftbusters/diamond-ssh/coolify/id_ed25519`) is available for later provisioning of the Coolify user.
