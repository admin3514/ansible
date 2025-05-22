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

*inventory files / hosts* - Stores the vm's information  <br>
*ansible.cfg* - configuration file <br>

<hr>

📄 **3. Inventory File (hosts)**  <br>

The inventory file is a core component of Ansible. It tells Ansible which hosts to manage, and optionally, how to connect to them.  <br>

🗂️ **What is an Inventory File?**  <br>
 - *A text file that lists the managed nodes (hosts).*  <br>
 - *You can group hosts and set variables like SSH user, port, and key.*  <br>
 - *Used in ad-hoc commands, playbooks, and roles.*  <br>

<hr>

*Ansible Installation on ubuntu :*

```ssh
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```

<hr>

*command for take access of host machine :*

```ssh
ansible -i hosts all -u ubuntu --private-key=./new-key.pem -m shell -a hostname
```

*command after adding username and private key in ansible.cfg file :*

```ssh
ansible -i hosts all  -m shell -a hostname
```

```ssh
ansible -i hosts all  -m shell -a 'echo "Hello World"'
```

<hr>

*To run .yaml file*

```ssh
ansible-playbook first.yaml
```

<hr>


**Variables** - name of memory location to store the data <br>
*Types of variable -*  <br>
1. local varible  <br>  
2. global variable  <br>
3. separate file variable  <br>
4. CLI variable ansible  <br>
```ssh
playbook playbook.yml -e "variable_name=value"
```
5. register variable  <br>
6. prompt variable  <br>
7. host variable   <br>
