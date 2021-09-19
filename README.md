# ansible_role_myimage


1. sudo apt install ansible
   
   create a folder where we will be creating the ansible roles and make a folder roles and run the below command  eg: ansible/roles/
   
3. ansible-galaxy init myimage // this will create default directorsy structure of ansible
4. in the ansible folder create main.yml  and paste below contents
    
   - hosts: all
     become: true
     roles:
       - myimage

host ssh ket
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCw4TojRWi5VNkpGfsFYXDPow3c1PikkEfS2YUzE7mJpCwQ9CbaKHQkN+1gmrRTClar/3EoHU7P+POFhCjUVgDf8+PHKPN7cYCqateNd61lSXAC+nfWNAYPXx1127OsBz4TAz7jqLWTsBWeVLmljWEoPimqPkh1KYClhjiXVzMqD++9cxXAVSc9FmT4eNEMHlyM8Fa3OZsheUPujzqK/ipTzYuLZ9H2r2kXUtPdOSjnyQGTlnY/tBP3pOjqvy0Wp1VKZPq0KrU9ZAsQQIqJoUlQA9x2nZcDl3F3DLb5pwZMuGs1I3ocWbVuxIBH5nnONx4ED89cgUdYPWcF15Y/LP148oZV2eYOsilMggW2LnO37HngtqlSCCiVaDLZ6kuQ4lYBRGmTD9bXT51ntC2F2xBHIYDJhBUaejK+Y7Qc9usEjquIBtuFIzkpoVPb36K3RjJuzNPGSY7i86pUNnPQHfnqDs3jsL3umWwDAHpS4z5ev0nZgqPSd5F3tniAfptB01c= root@vaibhav-VirtualBox
