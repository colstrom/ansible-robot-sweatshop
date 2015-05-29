# ansible-robot-sweatshop

[Robot Sweatshop](https://github.com/JScott/robot_sweatshop) - A lightweight, non-opinionated CI server

[![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)
[![Platforms](http://img.shields.io/badge/platforms-osx-lightgrey.svg?style=flat)](#)

## Tunables
- `robot_sweatshop_user` (string) - The user Robot Sweatshop runs processes under.
- `robot_sweatshop_group` (string) - The user group Robot Sweatshop runs processes under.
- `robot_sweatshop_log_root` (string) - Where Robot Sweatshop stores its logs.
- `robot_sweatshop_runtime_root` (string) - Where Robot Sweatshop stores its PID files.
- `robot_sweatshop_config_root` (string) - Where Robot Sweatshop finds its configs files.
- `robot_sweatshop_db_root` (string) - Where Robot Sweatshop stores its queue files.
- `robot_sweatshop_http_port` (integer) - The port that Robot Sweatshop's HTTP server runs on.
- `robot_sweatshop_http_bind` (string) - The host that Robot Sweatshop's HTTP server binds to.
- `robot_sweatshop_conveyor_port` (integer) - The port that the Conveyor runs on.
- `robot_sweatshop_payload_parser_port` (integer) - The port that the Payload Parser runs on.
- `robot_sweatshop_job_dictionary_port` (integer) - The port that the Job Dictionary runs on.
- `robot_sweatshop_worker_port` (integer) - The port that the Worker runs on.
- `robot_sweatshop_job_timeout` (integer) - The seconds Robot Sweatshop will wait before requeueing a claimed job.

## Dependencies
- [telusdigital.ruby](https://github.com/telusdigital/ansible-ruby/)
- [telusdigital.upstart](https://github.com/telusdigital/ansible-upstart/)

## Example Playbook
```
- hosts: servers
  roles:
    - role: telusdigital.robot_sweatshop
      robot_sweatshop_http_port: 8080
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
