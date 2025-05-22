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


✅ **What is a Playbook in Ansible?** <br>
An Ansible playbook is a YAML file that defines a series of tasks to be executed on one or more remote hosts. It is the main way to automate configuration, deployment, and orchestration using Ansible.  <br>


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
1. local varible - Defined within a play, task, or block using vars, valid only in that paricular block only  <br>  
2. global variable - applies across all plays and hosts. <br>
3. separate file variable - write in separate .txt file and called it when need <br>
4. CLI variable ansible - passed in cli <br>
```ssh
playbook playbook.yml -e "variable_name=value"
```
5. register variable - captures the output of a task using the register keyword for use in later tasks.  <br>
6. prompt variable - ask user for input variable <br>
7. host variable - defined per host in the inventory (static or dynamic), applying only to that specific host.  <br>

*Ansible Variable Precedence (High to Low) -*  <br>
1. CLI Variable - Defined using -e; highest precedence, overrides all others.  <br>
2. Prompt Variable - User input at runtime via vars_prompt; high precedence.  <br>
3. Local Variable - Defined with vars inside a play, block, or task.  <br>
4. Register Variable - Captures output of a task using register; available after task runs.  <br>
5. Separate File Variable - Variables from external files via vars_files or include_vars.  <br>
6. Host Variable - Defined per host in inventory; overrides group/global variables.  <br>
7. Global Variable - Set in ansible.cfg, environment vars, or inventory defaults; lowest.  <br>

<hr>

**Ansible Modules -**  

An Ansible module is a reusable, standalone script that performs a specific task on a target system — like installing packages, managing files, users, services, etc.  <br>

📘 *Key Characteristics:*  <br>
 - Modules are the building blocks of tasks in a playbook.  <br>
 - Each task in a playbook uses one module to do something.  <br>
 - Modules are idempotent — they make changes only if needed.  <br>
 - Ansible has hundreds of built-in modules and supports custom modules.  <br>

 🧱 *Example of Using a Module*  <br>

 ```ssh
- name: Install Apache using the yum module
  yum:
    name: httpd
    state: present
```

In this example:  <br>
 - yum is the module.  <br>
 - It ensures the package httpd is installed (state: present).  <br>


🔥 *Commonly Used Modules*  <br>

1. yum / apt - Install or remove packages
2. conditions: when - when perform
3. privilege (root user) - perform through root user
4. package - download particular package when we don't know package name
5. service / systemd - start, enable, stop, restart service
6. copy - copy files to remote host
7. file - manage file
8. line in file -
9. block in file -
10. tags -

<hr>
