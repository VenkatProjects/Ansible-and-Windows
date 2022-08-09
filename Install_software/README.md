## Before Performing Software installation, Need to take prerequisites  

> First Step, need to create new user if required.

#### Here created new user name called **win_admin** and provided admin rights to perform software installation

![1user](https://user-images.githubusercontent.com/67817741/183625081-81753c46-e0ab-4a71-9d14-ee3c3bfb765d.jpg)

Note: you can perform local user, Not necessary to create new user. 

> Then login to windows by using **win_admin**

![login](https://user-images.githubusercontent.com/67817741/183619159-4b2352fc-bef9-42aa-8396-61faf1caa271.JPG)


> Next Step, Install chocolatey package to the windows

	Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

The above command will **Set-ExecutionPolicy** through Powershell


> Then run the below script for admin remote privileges.

[Remote_Previliges](https://github.com/VenkatProjects/Ansible-and-Windows/blob/main/Install_software/Remote_Privileges.txt)

## Follow below prerequisites for Ansible Controller

> Install Pywinrm file

		pip install -y pywinrm
		
OR		

		pip3 install -y pywinrm
		
If you want to run specific user name, then follow 

		-m pip install --user --ignore-installed pywinrm

> Then,	
		
		yum install python2-winrm.noarch

> Install Chocolatey Packages in Ansible

		ansible-galaxy collection install chocolatey.chocolatey
	
> Last step to add or create Host file with below variables.

			[windows]
			
			[windows:vars]
		ansible_user=win_admin
		ansible_password=******
		ansible-port=5986
		ansible_connection=winrm
		ansible_winrm_scheme=https
		ansible_winrm_server_cert_validation=ignore
		
> Now, we need to check it is communicating with Windows machine or not

		ansible windows -m win_ping
		

**Most Important: if you get winrm or https connection error, then you need add winrmhttps in firewall or cloud console 

![winrm](https://user-images.githubusercontent.com/67817741/183627592-550bcf87-a5c9-4b30-99ca-c5ab61d39f11.JPG)

It is successfully communicating with windows machine.

![ping](https://user-images.githubusercontent.com/67817741/183627223-282ae3a4-188d-451c-8680-38a9853c5983.JPG)


> Now, Install softwares. 

![yaml](https://user-images.githubusercontent.com/67817741/183628457-9574cc2a-5605-4594-b158-34a384eadb2c.JPG)


	ansible-playbook install.yml 
	
Before installing google chrome softwares

![beforesoft](https://user-images.githubusercontent.com/67817741/183628746-400e8d5c-b82e-421d-bd61-495b01351416.JPG)

	
	notepadplusplus, putty, winscp