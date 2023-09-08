# Ansible playbook to deploy Castopod
This playbook will deploy simple [Castopod](https://castopod.org/) on your server. 

Tested on: 
 * Ubuntu: 18.04, 20.04, 22.04
 * Debian: 10, 11

Applications that will be installed on your server:
 * Mysql server 
 * Apache web server
 * Let's encrypt ssl certificate 
 * Castopod with file backend and without ffmpeg to run video clips

## Prerequisites
Before downloading this playbook, make sure you have everything done in list below:

 1. A clean Debian or Ubuntu server, that is accessible from internet
 This playbook is designed to run on clean installations and may broke something on your server if it has some applications installed on it
 2. Ability to connect to your server with ssh key and run sudo without asking password 
 3. Configured DNS record, that points to your web server
 4. Installed `ansible`, `jq` and `curl` on machine, that will run this playbook
    e.g. with `apt install ansible jq curl`

## Using this playbook
Simple instruction how to run this playbook:

 1. Clone repository:
 ```sh
 git clone https://github.com/belykhk/castopod-ansible-playbook.git
 ```
 2. Install ansible roles, used by this playbook:
 ```sh
 ansible-galaxy install -r requirements.yml
 ```
 3. Rename `inventory.yml.example` to `inventory.yml` and replace information in it 
 4. Run playbook:
 ```sh
 ansible-playbook -i inventory.yml deploy-castopod.yml
 ```

## What to do next
Open link `https://yourdomain/cp-login` and start using Castopod. It is good practice to secure you public facing server, but this is out of scope of this playbook (honestly, i'm just being lazy)

## License?
Nah, do whatever you want with this playbook. 

## Thanks
 * Castopod team 
 * Jeff Geerling 
