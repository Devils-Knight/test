# Security-Hardening
Instructions on how to **Harden** a System<br><br>

## Steps to run the ansible playbook (harden1)
***
1. Create a `hosts` file to include ip addresses of all your instances.<br>
&nbsp;&nbsp; In your hosts file, specify the path to the private key file you downloaded from AWS.<br>
&nbsp;&nbsp; Assuming the default login user is `ubuntu` (which for AWS is the case)
```
<ip_address> ansible_user=ubuntu ansible_ssh_private_key_file=/home/<...>.private_key.pem
```

2. Within `./roles/harden/tasks/main.yml`, set the hashed password for the `deploy user`.<br>
&nbsp;&nbsp; You can use the `mkpasswd` utility in Ubuntu for the same.<br>
&nbsp;&nbsp; You will be prompted to enter a new password. Once you hit return, the hash for the password you entered will be printed on screen.
```
mkpasswd --method=SHA-512 --stdin
```

3. Within `./roles/harden/tasks/main.yml`, set the proper path to your public SSH key, under the task named `Set authorized key taken from file`
4. From the root of the project, run `ansible-playbook -i hosts harden1.yml`

Note: all the commands are run as root user.

## Steps to run the ansible playbook (harden2)
***
1. Create a `hosts` file to include ip addresses of all your instances.
2. run `ansible-playbook harden2.yml -i hosts`
