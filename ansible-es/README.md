# ansible-elasticsearch

Create elasticsearch cluster via Ansible over CentOS*.

## Usage

### Requeriments
-  Ansible 2.0 or higher.

### Steps
#### 1. Install Ansible on your machine

  * **Via YUM:** http://docs.ansible.com/ansible/intro_installation.html#latest-release-via-yum
  * **Via APT:** http://docs.ansible.com/ansible/intro_installation.html#latest-releases-via-apt-ubuntu
  * **Via PIP:** http://docs.ansible.com/ansible/intro_installation.html#latest-releases-via-pip

For other systems, checkout the installation page of Ansible.
http://docs.ansible.com/ansible/intro_installation.html

#### 2. Clone this repo

```
git clone git@github.com:t1ger/playbook.git
cd ansible-es
```

#### 3. Edit and customize your hosts file.

#### 4. Run Ansible playbook. Check _Tags section_ and _Variables section_ to see other playbook run options.

```
ansible-playbook es.yml -i hosts _[options]
```

#### 5. Use elasticsearch !

* **How to Use:** https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html

## Playbook variables

Use command line variables as playbook input:

* **force_cleanup:** _[True/False]_ Force downloaded packages cleanup. Default or unknown value assumes False. 
```
ansible-playbook es.yml -i hosts -e force_cleanup=True 
ansible-playbook es.yml -i hosts -e force_cleanup=False 
```

## Playbook tags

Use tags to run a part of the playbook:

```
ansible-playbook es.yml -i hosts --tags es 
ansible-playbook es.yml -i hosts --tags "java,es" 
```

* **java / java_installation:** Install and configure jdk.
* **es_installation:** Get _es_ package if needed and install it.
* **es_configuration:** Set _es_ configuration needed, create service script and (re)start it.

## Group variables
#### GENERAL variables
* **package_download_path:** Path to download service packages (may be temp).

#### JAVA variables
#### ES variables
_coming soon_


