# Ansible-and-Windows
 ## Install and Update Software's in windows Using Ansible

We have written Ansible YAML script to create an EC2 Windows_server 

![image](https://user-images.githubusercontent.com/67817741/183588577-e96aef3e-6448-4134-bfef-963ef5601431.png)

While running, if you're getting any error. Please follow this Repo to get it resolved. [Ansible-Automation](https://github.com/VenkatProjects/Ansible_Automation.git)

Here pip and boto packages were already installed by using below commands

		sudo yum -y install python-pip
		sudo pip install boto boto3
	
	Now run the YAML Script 
		ansible-playbook Launch_EC2-Instance.yml

Before Running the Ansible script, We have two Instance Running in the Cloud Console

![Before_Windows](https://user-images.githubusercontent.com/67817741/183597740-98695861-9fdc-48b0-b478-a12b5783b872.JPG)

Now we have successfully launched

![Server_Launched](https://user-images.githubusercontent.com/67817741/183597945-379dc365-ff16-41b4-8ec9-40a7c353aaeb.JPG)

![After_Windows](https://user-images.githubusercontent.com/67817741/183597951-edb6f86a-fa42-4e44-911b-c713d9e8b1ed.JPG)

		