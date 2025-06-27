# Ansible-Apache-Automation-on-Localhost-WSL-Beginner-Friendly-Setup
# 📦 Ansible Apache Automation on Localhost (WSL)

This beginner-friendly Ansible project helps you automate the installation and configuration of the Apache Web Server on your **local WSL (Ubuntu)** environment. Perfect for learning Ansible automation without needing a remote server.

---

## 📁 Project Structure

ansible-apache-setup/
├── inventory # Ansible inventory file targeting localhost
├── playbook.yml # Main Ansible playbook
└── README.md # Project documentation

yaml
Copy code

---

## 🧩 What This Project Does

- Updates the system’s apt package cache
- Installs Apache web server
- Ensures Apache is running and enabled
- All done **locally** using `ansible_connection=local`

---

## 📝 Inventory File (`inventory`)

```ini
[webservers]
localhost ansible_connection=local
This makes Ansible execute tasks on your own machine (WSL) instead of SSHing into another host.

🧠 Playbook (playbook.yml)
yaml
Copy code
- name: Install Apache Web Server
  hosts: webservers
  become: yes
  tasks:
    - name: Update apt cache
      apt:
        update_cache: yes

    - name: Install Apache
      apt:
        name: apache2
        state: present

    - name: Ensure Apache is running
      service:
        name: apache2
        state: started
        enabled: yes
🚀 How to Run This Project
Open terminal inside the project directory:

bash
Copy code
cd ansible-apache-setup
Run the playbook:

bash
Copy code
ansible-playbook -i inventory playbook.yml
🌐 How to Verify Apache Installation
Make sure Apache is running:

bash
Copy code
sudo systemctl status apache2
Then open your browser and go to:

arduino
Copy code
http://localhost
You should see the Apache2 Ubuntu default welcome page.

💡 Requirements
Ubuntu on WSL (Windows Subsystem for Linux)

Ansible installed:

bash
Copy code
sudo apt update && sudo apt install ansible -y
🔰 Why This Project?
Simple setup for local learning

No SSH or remote server needed

Teaches real-world Ansible usage

🔄 Possible Extensions
Replace Apache with Nginx

Copy custom HTML files

Add user creation or firewall tasks

Convert to use remote inventory

✨ Built with ❤️ by Mohsin using Ansible & WSL

yaml
Copy code

---

Let me know if you'd like to add GitHub badge buttons (like “Run Playbook” or “Install Ansible”) to the README or want help turning this into a portfolio project!







