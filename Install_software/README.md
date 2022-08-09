## Before Performing Software installation, Need to take prerequisites  

> First Step, need to create new user if required.

#### Here created new user name called **win_admin** and provided admin rights to perform software installation

![user](https://user-images.githubusercontent.com/67817741/183619099-e5e8303d-4314-49c2-b374-df209bc752b6.jpg)



Note: you can perform local user, Not necessary to create new user. 

> Then login to windows by using **win_admin**

![login](https://user-images.githubusercontent.com/67817741/183619159-4b2352fc-bef9-42aa-8396-61faf1caa271.JPG)


> Next Step, Install chocolatey package to the windows

	Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

The above command will **Set-ExecutionPolicy** through Powershell


> Then run the below script to give amdin previleges.


