## INSTALL NGNIX ,DOTNET, JAVA THROUGH  ANSIBLE CONTROL NODE
---

###step to perform
 1. Create two  ubuntu vm's
 2. Enable the passwd authentication
   ```
   sudo vi /etc/ssh/sshd_config
   ```
   ![alt text](./images/images/image1.png)

  3. Restart the sshd service 
   
   ![alt text](./images/images/image2.png)

   4. Now create a user "devops" on both the instance
   
   ![alt text](./images/images/image3.png)

  5. Give sudo permissions to the users on both the instances

![alt text](./images/images/image4.png)

  6. Now login with devops user on both the instance
   ![alt text](./images/images/image5.png)

  7. Now create ssh_keygen on control node
  8. Now copy id  of the control node to the node1 by giving the private ip adress of node1
   ![alt text](./images/images/image6.png)


   ### NOW WE HAVE CONNECTED BOTH THE MACHINES

   9.  To check the create a hosts file with node1 private ipadresses and run the command
```
ansible -i hosts -m ping
```
it will give some output which looks like this in below
![alt text](./images/images/image9.png)


### NOW INSTALL ANSIBLE IN CONTROL NODE IN DEVOPS

```
sudo apt update
sudo apt install software-properties-common -y
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible -y
```
![alt text](./images/images/image7.png)

###  INSTALLING JAVA USING ANSIBLE

  1. Create two directories named as inventory playbooks
  2. In inventory create hosts file and give node1 private ip adresses
  3. In the playbooks directory write a play installing java
   
   ![alt text](./images/images/image11.png)

   ![alt text](./images/images/image12.png)


  4. Now run the command 
   ```
   ansible-playbook -i <inventory_path> <playbooks_path>
   ````
   ### NOW WE WILL SEE OUTPUT LIKE THIS
    
![alt text](./images/images/image13.png)
 
  Now check java version in node1

![alt text](./images/images/image14.png)



   ### INSTALLING DOTNET AND NGINX

1.  In the playbooks directory write a play installing nginx and dotnet
2. Now run the command 
   ```
   ansible-playbook -i <inventory_path> <playbooks_path>
   ````
3. Now we will see output like this

   ![alt text](./images/images/15%20(1).png)

   ### NOW CHECK THE NODE1 SEE THE THE INSTALLATIONS
     
     ![alt text](./images/images/15%20(2).png)





     

   
 
