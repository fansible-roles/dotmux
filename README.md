tmux
=========

An ansible role to install and configure tmux

Requirements
------------

* ansible >= 2.11.12

Role Variables
--------------

* `tmux_install`  - `(dict)`  - enable the tmux installation and list the packages to be installed  

* `tmux_plugin_dir` - `(str)` - the default tmux plugin installation directory.`(defaults "$HOME/.tmux/plugins")`  

* `tmux_plugins`  - `(list)`  - a list of plugins to be installed  

Dependencies
------------

None

Example Playbook
----------------

* Basic default usage:  
```yaml
    - hosts: servers
      roles:
         - { role: mrbrandao.tmux }
```

* Installing custom plugins:  
```yaml  
- hosts: servers
  vars:
    tmux_plugins:
      - url: "http://github.com/plugin/myplugin"
        dest: "{{ tmux_plugin_dir }}/myplugin"
        version: "main" # use the git branch or tag
  roles:
     - { role: mrbrandao.tmux }
```

License
-------

GPL-3.0-only

Author Information
------------------

@mrbrandao - Igor Brandao - https://github.com/mrbrandao
