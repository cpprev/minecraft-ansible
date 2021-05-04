# minecraft-ansible

---

:pushpin: This repository's aim is to provide ansible playbooks to deploy and run a minecraft server.

:pushpin: You will need to change one or two configuration variables in order for this to work on your infrastructure.

---

## What to change to adapt to your infrastructure

in file "hosts" :

    - change "ansible_host" variable to your remote host IP address
    - change "ansible_password" in case you need password ssh authentication
    - change "ansible_ssh_private_key_file" in case you need private key ssh authentication

in file "group_vars/all" :

    - change "user" and "group" variables to your remote host user
    - change "mc_dl_link" variable to the minecraft server download link you want to deploy 
      (currently 1.16.X, see : https://www.minecraft.net/en-us/download/server)

in file "roles/mc/templates/server.properties.j2" :

    - adapt to the server properties you want for your server (map size, slots, ...)

---

## Install the server prerequisites

    ansible-playbook -i hosts --become --ask-become-pass install-server.yml
    (after which you need to enter your sudo password if required on remote host

---

## Run the server (listens on port 25565)

    ansible-playbook -i hosts --become --ask-become-pass run-server.yml
    (after which you need to enter your sudo password if required on remote host)

## Stop the server (when command above is running)
    
    CTRL + C
