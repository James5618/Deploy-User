# Ansible Playbook: Create Users with SSH Key Auth and Passwordless Sudo

This Ansible playbook automates the creation of user accounts on remote Linux hosts. It sets up users with:

- SSH key-based authentication
- Membership in a dedicated `keyauth` group
- Passwordless sudo access via the `keyauth` group
- Secure `.ssh` directory setup with correct permissions
- Removal of any user-specific sudoers files

---

## Files
- **`inventory.ini`** – Basic Inventory File.
- **`create_users.yml`** – The main Ansible playbook.
- **`users.yml`** – A variables file containing the list of users to create.

---

## 🔧 `users.yml` Format

Define users in a YAML list. Example:

```yaml
users:
  - username: "user"
  - ssh_key: "ssh-rsa <keyhere>"
