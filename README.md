Dropbox deamon running in docker
================================

This role creates a docker container running the Dropbox deamon
The docker container used is : thomfab/docker-dropbox (https://registry.hub.docker.com/u/thomfab/docker-dropbox/)

Role Variables
--------------

Several variables can be set up.

The name used for the docker container :
  docker_dropbox_dockername: "dropbox"

The folder where dropbox conf is stored (incl the auth token) :
  docker_dropbox_config_dir: "/mnt/dropbox_conf"

The folder where dropbox data will be synced :
  docker_dropbox_data_dir: "/mnt/dropbox_data"

The user and group (and id) used as owner of the conf and data folders :
  docker_dropbox_user: "myuser"
  docker_dropbox_userid: 1001
  docker_dropbox_group: "users"
  docker_dropbox_groupid: 100

Example Playbook
----------------

Example :

    ---
    - hosts: servers
      roles:
        - role: thomfab.ansible-docker_dropbox
          docker_dropbox_dockername: "dropbox"
          docker_dropbox_config_dir: "/mnt/dropbox_conf"
          docker_dropbox_data_dir: "/mnt/dropbox_data"
          docker_dropbox_user: "myuser"
          docker_dropbox_userid: 1001
          docker_dropbox_group: "users"
          docker_dropbox_groupid: 100


License
-------

BSD
