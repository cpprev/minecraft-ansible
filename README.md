# Minecraft Server - Ansible deployment

---

:pushpin: This repository's aim is to provide ansible playbooks to deploy and run a minecraft server.

:pushpin: You will need to change one or two configuration variables in order for this to work on your infrastructure.

---

## What to change to adapt to your infrastructure

In file "hosts" :

    - Change "ansible_host" variable to your remote host IP address.
    - Change "ansible_password" in case you need password ssh authentication.
    - Change "ansible_ssh_private_key_file" in case you need private key ssh authentication.

In file "group_vars/all" :

    - Change "user" and "group" variables to your remote host user.
    - Change "mc_dl_link" variable to the minecraft server download link you want to deploy 
      (currently 1.16.X, see : https://www.minecraft.net/en-us/download/server).

In file "roles/mc/templates/server.properties.j2" :

    - Adapt the server properties you want for your server (map size, slots, ...).

---

## Install the server prerequisites

If sudo password is required on remote host :

    ansible-playbook -i hosts --become --ask-become-pass install-server.yml

Else :

    ansible-playbook -i hosts --become install-server.yml

---

## Run the server (listens on port 25565)

If sudo password is required on remote host :

    ansible-playbook -i hosts --become --ask-become-pass run-server.yml

Else :

    ansible-playbook -i hosts --become run-server.yml

## Stop the server (when command above is running)
    
    CTRL + C
