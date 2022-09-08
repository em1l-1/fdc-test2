Ansible Readme:
---------------

1. Install ansible version 2.10 from https://www.ansible.com/

verify the version using the following command.

# ansible --version
ansible 2.10 or later
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/local/lib/python3.8/dist-packages/ansible
  executable location = /usr/local/bin/ansible
  python version = 3.8.10 (default, Jun 29 2020, 05:46:05) [GCC 5.4.0 20160609]

2. install the following FDC supported Ansible roles from https://galaxy.ansible.com/dell-networking
	Use this command to install the latest version of the OS10 collection from Ansible Galaxy:
		- $ ansible-galaxy collection install dellemc.os10
	To install a specific version, a version range identifier must be specified. For example, to install the most recent version that is greater than or equal to 1.0.0 and less than 2.0.0:
		- $ ansible-galaxy collection install 'dellemc.os10:>=1.0.0,<2.0.0'

	Use this command to install the latest version of the OS9 collection from Ansible Galaxy:
		- $ ansible-galaxy collection install dellemc.os9
	To install a specific version, a version range identifier must be specified. For example, to install the most recent version that is greater than or equal to 1.0.0 and less than 2.0.0:
		- $ ansible-galaxy collection install 'dellemc.os9:>=1.0.0,<2.0.0'
	
	$ export ANSIBLE_NETWORK_GROUP_MODULES=os10,os9
		
3. Create a fabric and complete the "Network Configuration". Provide the Management IP address of each switch and CLI credentials.

4. Download the Ansible zip file from FDC which is available in "Configuration Download" and extract on the server where ansible got installed. The Zip file contains following files

    - ansible_readme.txt
    - ansible_deploy.sh
    - hosts
    - playbook.yml
    - host_vars folder and its contents (the yml files for each switch in the fabric)
    - templates folder and its contents (the cli command files for each switch in the fabric if required)

5. Provide executable permission for the file ansible_deploy.sh and execute it. Check for the execution status on the console

6. Please make sure that the host key is saved in the ansible server. For more information http://docs.ansible.com/ansible/latest/user_guide/intro_getting_started.html#host-key-checking