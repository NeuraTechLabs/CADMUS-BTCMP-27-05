Ansible topology with one Windows host

Files:

- inventory.ini: defines a single Windows host `windows1`.
- group_vars/windows.yml: group variables including `ansible_host_image: windows-10-x86_64`.
- playbook.yml: simple playbook using `win_ping` to verify connectivity.

Usage:

1. Update `ansible_host` in `inventory.ini` to the real IP of your Windows VM.
2. Secure `ansible_password` (use Ansible Vault in production).
3. Run:

```bash
ansible-playbook -i ansible/inventory.ini ansible/playbook.yml
```

Notes:
- The image name is recorded in `group_vars/windows.yml` as `windows-10-x86_64`.
- Ensure WinRM is enabled and reachable on the Windows image.
