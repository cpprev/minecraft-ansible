# Install the server prerequisites

    ansible-playbook -i hosts --become --ask-become-pass --extra-vars "ansible_password=toto123lol" full.yml

# Run the server

    ansible-playbook -i hosts --become --ask-become-pass --extra-vars "ansible_password=toto123lol" run-server.yml
