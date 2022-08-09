## Before Performing Software installation, Need to take prerequisites  

> First Step, need to create new user if required.

### Here created new user name called **win_admin** and provided admin rights to perform software installation

Note: you can perform local user, Not necessary to create new user. 

> Then login to windows by using **win_admin**

> Next Step, Install chocolatey package to the windows

	Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

The above command will Powershell **Set-ExecutionPolicy** 

> 
