# ansible_role_myimage


1. sudo apt install ansible
   
   create a folder where we will be creating the ansible roles and make a folder roles and run the below command  eg: ansible/roles/
   
3. ansible-galaxy init myimage // this will create default directorsy structure of ansible
4. in the ansible folder create main.yml  and paste below contents
    
   - hosts: all
     become: true
     roles:
       - myimage
