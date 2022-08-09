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

		python3 -m pip install --user --ignore-installed pywinrm

> Then,	
		
		yum install python2-winrm.noarch

> Install Chocolatey Packages in Ansible

		ansible-galaxy collection install chocolatey.chocolatey
	
> Last step to add or create Host file with below variables.

		[windows]
		
		34.239.106.213
	**you need to enter public ip when you're performing from VM or Hyper.**
	

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

After Run, 

![succeed](https://user-images.githubusercontent.com/67817741/183629601-1dbaac79-0670-41d2-9828-38a341268196.JPG)

Now Successfully installed Google chrome browser.

![aftersoft](https://user-images.githubusercontent.com/67817741/183629596-42067333-161a-48e9-ba6b-0c918a02a5ae.JPG)


If you want perform Mulitiple Applications then follow below.


![muliple](https://user-images.githubusercontent.com/67817741/183630450-76f1d327-7a00-43e3-a780-5d25f6cf51a2.J


![muliplesucced](https://user-images.githubusercontent.com/67817741/183630438-6ad22263-b68e-48a5-ba5c-f5afa52d88c0.JPG)




	
	
	
	