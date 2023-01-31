##  **AUX PROJECT 1 (SHELL SCRIPTING) TO ONBOARD DEVELOPERS TO HAVE CONTROLLED ACCESS TO MY SERVER**

## STEP 1 – CREATING .SH FOLDER


### creating the onboarding script

`vi onboard.sh`

![onboard-script2](./images/onboard-script2.PNG)
![capture_1](./images/capture_1.PNG)
![capture11](./images/capture11.PNG)

### copying onboard file into my ubuntu instance using my public IP address

`scp -i auxkeypair.pe onboard.sh ubuntu@44.203.139.93:~/;`

![onboard](./images/onboard.PNG)

### Connecting to the remote server

`ssh -i "auxkeypair.pem" ubuntu@ec2-3-83-246-203.compute-1.amazonaws.com`

![mkdirshell](./images/mkdirshell.PNG)

### Confirming presence of the file copied into the remote server

`ls -l`

![ls-l](./images/ls_l.PNG)

### Creating the project directory called 'shell'

`mkdir shell`

![ls-l](./images/ls_l.PNG)

### Moving the onboard.sh file to the shell folder

`move onboard.sh /home/ubuntu/shell/`

![move-onboard](./images/move-onboard.PNG)

### Changing directory into shell folder

`cd shell`

![cd-shell](./images/cd-shell.PNG)

### Confirming availability of onboard file in the shell folder

`ls`

![shell-ls](./images/shell-ls.PNG)

### Creating files for public and private keys as well as names.csv 

`touch id_rsa id_rsa.pub names.csv`

![touch-id-rsa](./images/touch-id-rsa.PNG)

### Populating the id_rsa.pub file

`vi id_rsa.pub`

![idrsapub1](./images/idrsapub1.PNG)
![idrsapub](./images/idrsapub.PNG)

### Populating the id_rsa file

`vi id_rsa`

![idrsaprivate](./images/idrsaprivate.PNG)

### Populating the id_rsa file

`vi names.csv`

![vi-names](./images/vi-names.PNG)

### Populating the id_rsa file

`vi names.csv`

![vi-names](./images/vi-names.PNG)

### Creating developers group

`sudo groupadd developers`

![sudogroupadd](./images/sudogroupadd.PNG)

### Making the scrip onboard.sh executable 

`sudo chmod +x onboard.sh`

![sudochmod](./images/sudochmod.PNG)

### Executing the onboard.sh script without sudo priviledge

`./onboard.sh`

![execute-without-sudo](./images/execute-without-sudo-priviledge.PNG)

### Changing to super user

`sudo su`

![change-to-supauser](./images/change-to-supauser.PNG)

### Executing the onboard.sh script with sudo priviledge

`./onboard.sh`

![runningonboard](./images/runningonboard.PNG)

### Confirming existence of the created users in the home directory

`ls -l /home/`

![ls-l](./images/ls-l.PNG)

### Confirming the developer group already created

`getent group developers`

![getentdevelopers](./images/getentdevelopers.PNG)

### Confirming the detail of developer group

`cat /etc/passwd`

![catetcpasswd](./images/catetcpasswd.PNG)

### For further filtering and text analysing

`cat /etc/passwd | awk -F':' '{ print $1}' | xargs -n1 groups`

![filtering](./images/filtering.PNG)

## LAST STEP – TESTING THE USERS RANDOMLY

### creating .pem private key on the developer window

`ssh -i aux-proj.pem Raymond@100.24.42.23`

`ssh -i aux-proj.pem Collins@100.24.42.23`

![privkey4developers](./images/privkey4developers.PNG)

![asraymond](./images/asraymond.PNG)

![as-another-user](./images/as-another-user.PNG)

### To confirm the users actually do not have sudo priviledg

`sudo apt update`

![sudo-right-confirmation](./images/sudo-right-confirmation.PNG)

![![sudo-right-confirmation](./images/ls-la.PNG)
](./images/ls-la.PNG)

![ls-la-ssh](./images/ls-la-ssh.PNG)

![catcollins](./images/catcollins.PNG)




