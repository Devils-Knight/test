# Docker-Setup
**Docker**: This is the project directory containing all variable files and main playbook.<br><br>
**vars/default.yml**: Variable file resides in vars directory through which you are going to customize the playbook settings.<br><br>
**docker.yml**: Here, you are going to define the task that is going to execute on the remote server.
***
## Settings

- `create_containers`: number of containers to create.
- `default_container_name`: default name for new containers.
- `default_container_image`: default image for new containers.
- `default_container_command`: default command to run on new containers.


## Running this Playbook

Quick Steps:

### 1. Obtain the playbook
```shell
git clone https://github.com/Devils-Knight/test
cd test/Docker
```

### 2. Customize Options

```shell
nano vars/default.yml
```

```yml
#vars/default.yml
---
create_containers: 4
default_container_name: docker
default_container_image: ubuntu
default_container_command: sleep 1d
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] playbook.yml
    eg. ansible-playbook playbook.yml -l server1 -u rocky
```
***