# configuration-management

🔗 **Project page:** [https://roadmap.sh/projects/configuration-management](https://roadmap.sh/projects/configuration-management)

Ansible Server Setup Project  
  
This project automates the setup of a basic web server using Ansible.
It installs and configures essential tools, deploys a static website, and manages SSH keys — all through  
  
⚙️ Roles Overview
base — updates system packages and installs basic utilities (e.g. fail2ban, curl, vim).
nginx — installs and configures Nginx web server.
app — creates an archive from index.html, uploads it, and deploys it to /var/www/html.
ssh — adds a public SSH key to the target server.

🚀 Usage

Edit inventory.ini and add your server:

[web]
your_server_ip ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa

Run all roles:
ansible-playbook -i inventory.ini setup.yml

Run a specific role:
```bash
ansible-playbook -i inventory.ini setup.yml --tags app
```

🧰 Requirements
Run these on your local machine (where you execute Ansible):
```bash
sudo apt install ansible zip -y
```

On the remote server, the base role ensures needed packages like tar and unzip are installed automatically.
