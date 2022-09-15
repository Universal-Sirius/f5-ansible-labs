# Ansible F5 Automation IMmersion Day Workshop
You will use Ansible commands and playbooks to explore and reconfigure a F5 in a virtual environment.  Note, that even though we are using a virtual environment, this is not a requirement, everything we do, can be done on physical devices.   

The Immersion Day is meant as a follow on to the Network Automation Immersion Day.  Some content will be review but in respect to using Ansible with F5.  While you can go through these labs there may be concepts that were covered previously that we will not cover as it is expected that these concepts are already understood.  Throughout the labs we hope to share some additional features, elements, good and bad practices and patterns to using Ansible for Automation. 

You will be required to modify some files during the course of this workshop.  You will not be required to write your own playbooks as this would require much more time.  The playbooks used are open source and thus free to use and modify.  That being said, writing playbooks and running them in a test environment is one of the best ways to learn.   
## Outline
* Part 1: Getting setup
    * Fork Git Repo
    * SSH to jump station 
    * Connecting to F5 
    * Downloading forked Git Repo 
* Part 2: Basic F5 labs 
  * Explore the lab environment 
  * Modify files in Git Repo 
  * Gather data from F5 
  * Adding nodes to F5 
  * Adding a load balancing pool 
  * Adding members to a pool 
  * Adding a virtual server 
  * Adding and attaching an iRule to a virtual server 
  * Save the running configuration 
* Part 3: F5 operational labs 
  * Disabling a pool member 
  * Deleting F5 configuration 
  * Error Handling 
* Part 4: F5 AS3 labs 
  * Intro to AS3 
  * Operational change with AS3 
  * Deleting a web application 
* Part 5: Tower labs 
  * Explore Ansible Tower 
  * Create an Ansible Tower job template 
  * Create an Ansible Tower workflow 
  * Create a node maintenance workflow 

***Note:  Assume the output shown in the examples below will be different to yours.***

## Part 1: Getting setup
### Overview
* Fork the lab github repository to your own repository so you can edit and modify. 
* Accessing the jump station 
* Downloading your forked repository to the jump station 

### Fork the Sirius Ansible networking GitHub Repository
1. Login to [Github](https://github.com)
1. Go to [https://github.com/mysidlabs/f5-ansible-labs](https://github.com/mysidlabs/f5-ansible-labs)
1. Click on the Fork button in the upper-right section of the page:
![](images/image002.png)
***Note: Once forked, you can modify all files within Github***
### Connect to your jump host
*Step 1*
SSH to your jump box at `siduser###.jump.mysidlabs.com `

For MacOS or Linux users the following is an example using the terminal: 

```bash
$ ssh siduser<user_id>@siduser<user_id>.jump.mysidlabs.com 
```
e.g.
```bash
$ ssh siduser101@siduser101.jump.mysidlabs.com
```
You may get the following message, type **yes** at the prompt:
```bash
The authenticity of host 'siduser101.jump.mysidlabs.com (3.132.28.93)' can't be established. 
ECDSA key fingerprint is SHA256: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx 

Are you sure you want to continue connecting (yes/no/[fingerprint])? Yes 

Warning: Permanently added 'siduser.jump.mysidlabs.com,3.132.28.93' (ECDSA) to the list of known hosts. 
```

Note: You can remove from known hosts when workshop is completed. 

When prompted for your password type in the password the instructor provides 

password: ******* 

 

For Windows users the following is an example using Putty: 

 Type jump.mysidlabs.com in the Host Name box and click the Open button 

User and password for F5 BigIP: admin  / Mys1dlabspw!