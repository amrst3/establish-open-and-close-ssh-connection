# establish-open-and-close-ssh-connection
=========================================
* In this case i assume we are using linux based system

# Establish the configration :
-----------------------------
  # Client side :
-----------------
   * navigate to the home directory: ```cd```
   * install ssh client: ```sudo apt install ssh-client```
   * create directory and name it .ssh: ```mkdir .ssh```
   * enter .ssh directory: ```cd .ssh```
   * generat your public and private keys: ```ssh-keygen``` >> this will ask you to chose a path to save the keys, i recommend to leave the default and hit enter
   * now list .ssh content while standing in it: ```ls```
   * print the content of the file that ends with '.pub': ```cat id_???????.pub``` >> we will need it to authenticate with the server

  # Server side :
-----------------
   * navigate to the home directory: ```cd```
   * install ssh server: ```sudo apt install ssh-server```
   * create directory and name it .ssh: ```mkdir .ssh```
   * enter .ssh directory: ```cd .ssh```
   * create file and name it authorized_keys: ```touch authorized_keys```
   * open this file using nano: ```nano authorized_keys```
   * write the public key of the client you want to add in one line (write all the content of the id_???????.pub file)
   * hit 'ctrl+x' then hit 'y' to save then hit enter

# Open connection :
-------------------
  * in the server pc run ```ip -h address``` to get it's ip >> if your server is a virtual machine make sure to modify it's connection to pridged
  * in the client pc run: ```ssh user@192.168.?.?``` >> user= the username of the acount you want to login in the server, 192.168.?.?= the server's ip address
  * it will ask you if you are sure to connect: type yes and hit enter, then type the password of the user you want to login in the server and hit enter again
  * then  BOOM  you are in.

# Close connection :
  * just type 'exit' in the client pc and hit enter
