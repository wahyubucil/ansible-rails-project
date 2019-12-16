## Rails Passenger config on Ubuntu 18.04

Note: This is not a role. It's a full configuration. Only work on Ubuntu 18.04.

### How to setup

1. Make sure you have Ansible installed :)
2. Copy `ansible.cfg.example` to `ansible.cfg`

```sh
$ cp ansible.cfg.example ansible.cfg
```

3. Change the **private_key_file** and **remote_user**

4. Copy `inventory.example` to `inventory`

```sh
$ cp inventory.example inventory
```

5. Change the **remote** IP
6. Change the **ansible_python_interpreter** with your local Python interpreter. Please use python3 interpreter!

### How to use

Run this command to init / setup the server :

```sh
$ ansible-playbook playbook_init.yml
```

If you only need to setup some items, run with specific tags. Example :

```sh
$ ansible-playbook playbook_init.yml --tags "nginx,ruby"
```

Run this command to deploy the app :

```sh
$ ansible-playbook playbook_deploy.yml
```

Note: If you choose **no** on the deploy key question. It will generate the deploy key if it doesn't exist. You can get the deploy key from the error message.

Made with 💚 by [Wahyu Bucil]. Enjoy :)

## License

MIT

[wahyu bucil]: https://github.com/wahyubucil
