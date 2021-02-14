# auxilliary-projects

Created shell directory
changed to shell directory
created the file names.csv for users to be added
created creatingusers file
Also within shell directory .. I sudo bash creatingusers (sudo bash starts a new bash shell with the security privilege of root user)

Switched to home directory 
created .ssh directory
Inside .ssh directory - where i created an authorized_keys files (id_rsa & id_rsa).pub and added the given public and private key respectively.

Added developers group as it wasn't added before

created onboardingusers file

#!/bin/bash
userfile=$(cat names.csv)
    if [ $(id -u) -eq 0 ]; then
# Reading the CSV file
    for user in $userfile;
    do
            echo $user
        if id "$user" &>/dev/null
        then
            echo "User Exist"
        else
# This will create a new user
        useradd -m -d /home/$user -s /bin/bash -g developers $user
        echo "New User Created"
        echo
# This will create a ssh folder in the user home folder
        su - -c "mkdir ~/.ssh" $user
        echo ".ssh directory created for new user"
        echo
# We need to set the user permission for the ssh dir
         su - -c "chmod 700 ~/.ssh" $user
         echo "user permission for .ssh directory set"
         echo
# This will create an authorized-key file
        su - -c "touch ~/.ssh/authorized_keys" $user
        echo "Authorized Key File Created"
        echo
# We need to set permission for the key file
        su - -c "chmod 600 ~/.ssh/authorized_keys" $user
        echo "user permission for the Authorized Key File set"
        echo
# We need to create and set public key for users in the server
        cp -R "/home/shollay/.ssh/id_rsa.pub" "/home/$user/.ssh/authorized_keys"
        echo "Copyied the Public Key to New User Account on the server"
        echo
        echo
        echo "USER CREATED"
            fi
        done
    else
    echo "Only Admin Can Onboard A User"
    fi

Korede
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Dammy
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server


USER CREATED
Deji
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Siju
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Dayo
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Kayode
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Dejo
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Sanjo
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Demola
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Bayo
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Deola
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Dele
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Bingo
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Dele
User Exist
Banjo
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Dara
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Kore
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Ayo
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Segun
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED
Bandele
New User Created
.ssh directory created for new user
user permission for .ssh directory set
Authorized Key File Created
user permission for the Authorized Key File set
Copyied the Public Key to New User Account on the server

USER CREATED




