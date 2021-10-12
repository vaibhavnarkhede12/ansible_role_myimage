# ansible_role_myimage


1. sudo apt install ansible
   
2. create a folder where we will be creating the ansible roles and make a folder roles and run the below command  eg: ansibletesting
````
- ── main.yml
- ── roles
    - └── ansible_role_myimage
      -    ├── files
              -  └── init-script.bash
      -    ├── README.md
      -    └── tasks
              -  └── main.yml
````
   
3. In main.yml copy below 4 lines
     -    (if ansible needs to run on localhost give host as localhost)

````
   - hosts: all 
     become: true 
     roles: 
      - ansible_role_myimage

````
5. if ansible needs to be run on a slave machine 
   edit the /etc/ansible/hosts file in main machine and add the Ip of slave machine anywhere there 
   and make sure the " hosts: all " is specified in the main.yml file 

6. you can write ansible tasks in the main.yml file in tasks folder 
7. follow the SSH-KEYS section now 

8. once SSH connection works you can run the ansble using 

``   -  ansible-playbook -u root /mnt/ansibletesting/main.yml  ``

( go to ansiblerole_myimage folder
   and run the command 
   ansibe-playbook --connection=local ./main.yml)
   
#############################################################################################   
############################### SSSH KEYS ###################################################
#############################################################################################

* there are two machines 
   main refers to ansible 
   host refers to the slave machine in which we will remotely execute ansible 

 * GO to the root profiles in both systems
 * in the both machine install ssh clients
   ``  sudo apt-get install openssh-client openssh-server``
 * in the slave machine 
 ```
   * go to /etc/ssh/sshd_config file and change three params
      PermitRootLogin yes
      AuthorizedKeysFile .ssh/authorized_keys
   * systemctl restart sshd
 ```
 * in the main machine , 
 ```
   * create SSH keys : ssh-keygen  ( do not give any passwords , just hit enter)
   * copy the ssh key create in /root/.ssh/id_rsa.pub to the slave machine path /root/.ssh/authorized_keys
   * restart the ssh daemon in slave machine ( systemctl restart sshd )
   * try to ssh in the slave using ssh root@IpOfSlaveMachine  ( IP command ifconfig)
 ```

###########################################################################################

ansible-playbook -u vaibhav --private-key /root/.ssh/id_rsa.pub -i 192.168.1.106 /mnt/ansibletesting/main.yml
