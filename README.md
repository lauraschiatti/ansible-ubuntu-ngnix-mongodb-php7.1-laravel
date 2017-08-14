## Laravel + Nginx + PHP7.1 + MongoDB Deployment using Ansible 

- Requires Ansible 2.0+
- Expects Ubuntu hosts
- Expects Laravel 5.x App to be deployed

#### 1- Install Ansible 
     $ sudo apt-get update
     $ sudo apt-get install ansible 
           
#### 2- Generate a RSA Key Pair for authentication without password on the client machine
     $ ssh-keygen -t rsa
     $ ssh-keygen -t rsa -b 2048 -v     
      
     Once you have entered the Gen Key command, you will get a few more questions, you can press enter here.
     
#### 3- Copy the public on the virtual server that we want to use
     $ ssh-copy-id <ssh_remote_user>@<your-ip-address>
                 
#### 4- Clone Ansible Repository
     $ git clone https://github.com/lauricdd/ansible-ubuntu-ngnix-mongodb-php7-laravel.git
      
#### 5- Customize hosts file
     $ cd ansible-ubuntu-ngnix-mongodb-php7.1-laravel
     $ nano hosts

     output-example:
     [<staging>]
     <your-ip-address>

#### 6- Customize vars file
     $ nano vars.yml
  
#### 7- Run deploy.yml ansible playbook
     $ cd ansible-ubuntu-ngnix-mongodb-php7-laravel
     $ ansible-playbook -i hosts main.yml

#### 8- Check on browser 
     https://<your-ip-address>
