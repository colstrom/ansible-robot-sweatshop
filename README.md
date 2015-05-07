# ansible-robot-sweatshop

[Robot Sweatshop](https://github.com/JScott/robot_sweatshop) - A lightweight, unopinionated CI server

[![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)
[![Platforms](http://img.shields.io/badge/platforms-osx-lightgrey.svg?style=flat)](#)

## Tunables
- `robot_sweatshop_user` (string) - The user Robot Sweatshop runs processes under.
- `robot_sweatshop_group` (string) - The user group Robot Sweatshop runs processes under.
- `robot_sweatshop_log_root` (string) - Where Robot Sweatshop stores its logs.
- `robot_sweatshop_runtime_root` (string) - Where Robot Sweatshop stores its PID files.
- `robot_sweatshop_config_root` (string) - Where Robot Sweatshop finds its configs files.
- `robot_sweatshop_db_root` (string) - Where Robot Sweatshop stores its queue files.
- `robot_sweatshop_http_input_port` (integer) - The port that Robot Sweatshop's HTTP server runs on.
- `robot_sweatshop_http_input_host` (string) - The host that Robot Sweatshop's HTTP server runs on.

## Dependencies
- [telusdigital.ruby](https://github.com/telusdigital/ansible-ruby/)
- [telusdigital.upstart](https://github.com/telusdigital/ansible-upstart/)

## Example Playbook
```
- hosts: servers
  roles:
    - role: telusdigital.robot_sweatshop
      robot_sweatshop_http_input_port: 8080
      robot_sweatshop_jobs:
        - name: build
          branch_whitelist:
            - master
          commands:
            - git clone git@bitbucket.org:me/mycode.git
            - cd mycode; rspec
          environment:
            RAILS_ENV=test
```

## License
[MIT](https://tldrlegal.com/license/mit-license)

## Contributors
- [Justin Scott](https://jvscott.net) | [e-mail](mailto:jvscott@gmail.com) | [Twitter](https://twitter.com/AKindlyOrc)
