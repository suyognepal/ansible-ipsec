# ansible-ipsec

# IPsec Ansible Playbook

This playbook automates the configuration of IPsec VPN using Ansible.

## Prerequisites

- Ansible installed on the control node.
- SSH access to the target hosts.
- Properly configured inventory file (`inventory/ipsec.ini`).

## Usage

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/suyognepal/ipsec-ansible.git
   ```

2. Navigate to the project directory:

   ```bash
   cd ipsec-ansible
   ```

3. Modify the `inventory/ipsec.ini` file to include your target hosts.

4. Update the `roles/strongswam/vars/main.yml` file with your IPsec configurations and secrets.

5. Run the playbook:

   ```bash
   ansible-playbook -i inventory/ipsec.ini vpn.yml
   ```

## Directory Structure

- `inventory/`: Contains inventory files.
- `roles/`: Directory containing Ansible roles.
  - `strongswam/`: Role for configuring StrongSwan IPsec.
    - `files/`: Files to be copied to the target hosts.
    - `handlers/`: Ansible handlers.
    - `tasks/`: Tasks to be executed.
    - `templates/`: Jinja2 templates.
    - `vars/`: Variables used within the role.
- `vpn.yml`: Main playbook file.

## Additional Notes

- Make sure to review and understand the playbook tasks and variables before running it in a production environment.
- This playbook assumes basic familiarity with Ansible and IPsec configuration.
- Always test the playbook in a non-production environment before deploying to production.

## License

This project is licensed under the [MIT License](LICENSE).
