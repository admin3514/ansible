# ansible

📌 **1. What is Ansible?**

Ansible is provisioning and configuration management tool  <br>

**- Open-source automation tool for :**  <br>
 - *Configuration management*  <br>
 - *Application deployment*  <br>
 - *Provisioning (e.g., cloud infrastructure)*  <br>

**- Uses SSH for communication (agentless).**  <br>
**- Written in Python, config in YAML (playbooks).**  <br>
**- Works on port 22** <br>
**- Works on push based mechanism**  <br>

<hr>

📂 **2. Directory Structure**  <br>

```ssh
project/
├── inventory.ini
├── playbook.yml
├── roles/
│   └── web/
│       ├── tasks/
│       │   └── main.yml
│       └── templates/
```

<hr>

📄 **3. Inventory File (hosts)**  <br>

The inventory file is a core component of Ansible. It tells Ansible which hosts to manage, and optionally, how to connect to them.  <br>

🗂️ **What is an Inventory File?**  <br>
 - *A text file that lists the managed nodes (hosts).*  <br>
 - *You can group hosts and set variables like SSH user, port, and key.*  <br>
 - *Used in ad-hoc commands, playbooks, and roles.*  <br>

<hr>

