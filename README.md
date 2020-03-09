OhMyZsh
=======

Setup
```
sudo apt-get update -y && sudo apt-get upgrade -y && sudo apt-get install ssh git ansible -y && git clone https://github.com/Francommit/ansible-ohmyzsh.git
```

Running
```
&& sudo ansible-playbook -i hosts setup.yml
```

Compatibility
-------------

Tested and approved on :

* Debian Stretch WSL

Role Variables
--------------

```yaml
# Choose user who you want to install oh my zsh for
ohmyzsh_users:
  - username: ops
    usergroup: admin
    home: /home/ops
  - username: root
    usergroup: root
    home: /root

ohmyzsh_plugins: git colored-man-page colorize extract history npm symfony2 httpie zsh-syntax-highlighting
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: jebovic.ohmyzsh }
```

Example : config
----------------

```yaml
# Configure oh-my-zsh for your user
ohmyzsh_users:
  - username: me
    usergroup: me
    home: /home/me
ohmyzsh_plugins: git colored-man-page colorize extract history zsh-syntax-highlighting
```

Tags
----

* ohmyzsh_config : only update config

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
