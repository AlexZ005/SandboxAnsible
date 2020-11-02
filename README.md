# 1. Configuring the environment

```shell
sudo -H pip install ansible==2.7.0.0
```

# 2. Executing playbooks

```shell
sudo ansible-playbook -i "localhost," -c local myplaybook.yml -C
```

-C, --check - executing with this parameter the playbook would not do any chages  
https://docs.ansible.com/ansible/latest/user_guide/playbooks_checkmode.html


# 3. Making some scripts

```bash
mkdir /opt/app
### Spoofing app outputs
cat << \EOF > /opt/app/myapp
#!/bin/bash
#echo '$0 = ' $0
#echo '$1 = ' $1
if [ "$1" == "list-running-instances" ]; then
    echo "Server PID:   Instance Path:"
elif [ "$1" == "login" ] && [ "$2" == "admin" ]; then
    echo "login success"
fi
EOF
chmod +x /opt/app/myapp

```

# 4. Linter

```shell
sudo -H pip install ansible-lint
```


# 5. Limitations:
https://cloud.google.com/shell/docs/limitations  
available free for all users