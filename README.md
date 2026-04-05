# rs_dragonwilds

This role installs and configures RuneScape: Dragonwilds dedicated server.

# dependencies

- `steamcmd` (e.g. role [`hofnarrr.steamcmd`](https://github.com/hofnarrr/ansible-role-steamcmd/))

# usage

Install the role and use it in your playbooks:

    $ ansible-galaxy role install hofnarrr.rs_dragonwilds

    $ cat playbook.yml
    - hosts: rsdw
      become: yes

      vars:
        # required vars - values are examples
        rs_dragonwilds_server_name: My RSDW Server
        rs_dragonwilds_default_world_name: myworld
        rs_dragonwilds_owner_id: 0123abc456def7890123abc456def789
        rs_dragonwilds_world_password: my-server-password
        rs_dragonwilds_admin_password: change-this-admin-password!

        # optional vars
        rs_dragonwilds_server_port: 1337
        rs_dragonwilds_unsupported_change_max_players: true
        rs_dragonwilds_max_players: 12

      roles:
        - hofnarrr.steamcmd  # steamcmd is required
        - hofnarrr.rs_dragonwilds

Check [`defaults/main.yml`](defaults/main.yml) for all configuration options.
