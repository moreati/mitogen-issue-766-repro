### Reproduction Instructions

1. Create Virtual Environment

   ```virtualenv -p python3.8 .venv```

2. Enter Virtual Environment

   ```source .venv/bin/activate```

3. Install python requirments

   ```pip3 install -r requirements.txt```

4. Install ansible requirements

   ```ansible-galaxy collection install -p collections -r requirements.yml```

5. Start netconf server container

   ```docker run -it --name sysrepo -p 830:830 --rm sysrepo/sysrepo-netopeer2:latest```

6. Run playbook with normal strategy

   ```ansible-playbook playbook.yml --extra-vars=strategy=linear```

7. Run playbook with mitogen strategy

   ```ansible-playbook playbook.yml --extra-vars=strategy=mitogen_linear```