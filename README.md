# minecraft-ansible

---

:pushpin: This repository's aim is to provide ansible playbooks to deploy and run a minecraft server.

:pushpin: You will need to change one or two configuration variables in order for this to work on your infrastructure.

---

### What to change to adapt to your infrastructure

    file "hosts" :
    - change "ansible_host" variable

    file "group_vars/all" :
    - change "user" and "group" variables
    - change "mc_dl_link" variable to the minecraft server download link you want to deploy 
      (currently 1.16.X, see : https://www.minecraft.net/en-us/download/server)

    file "roles/mc/templates/server.properties" :
    - adapt to the server properties you want to use for your server

### Install the server prerequisites

    ansible-playbook -i hosts --become --ask-become-pass --extra-vars "ansible_password=toto123lol" install-server.yml

### Run the server (listens on port 25565)

    ansible-playbook -i hosts --become --ask-become-pass --extra-vars "ansible_password=toto123lol" run-server.yml

### Stop the server (when command above is running)
    
    CTRL + C
