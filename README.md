# What to change to adapt to your infrastructure

    file "hosts" :
    - change ansible_host variable

    file "group_vars/all" :
    - change user and group variables
    - change mc_dl_link variiables to the minecraft server version you want to deploy

    file "roles/mc/templates/server.properties" :
    - adapt to the server properties you want to use for your server

# Install the server prerequisites

    ansible-playbook -i hosts --become --ask-become-pass --extra-vars "ansible_password=toto123lol" install-server.yml

# Run the server (listens on port 25565)

    ansible-playbook -i hosts --become --ask-become-pass --extra-vars "ansible_password=toto123lol" run-server.yml

# Stop the server (when command above is executed and running)
    
    CTRL + C
