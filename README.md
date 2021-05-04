# Install the server prerequisites

    ansible-playbook -i hosts --become --ask-become-pass --extra-vars "ansible_password=toto123lol" install-server.yml

# Run the server (listens on port 25565)

    ansible-playbook -i hosts --become --ask-become-pass --extra-vars "ansible_password=toto123lol" run-server.yml

# Stop the server (when command above is executed and running)
    
    CTRL + C
