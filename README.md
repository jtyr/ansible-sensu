Sensu-server
=======

Role to install Sensu-server and Sensu-client.  Installs dependencies of Redis and Rabbitmq-Server.

By default Server is not installed.
By default Client is installed.

Example
-------

```
---

- hosts: myhost
  roles:
    - role: sensu
      vars:
        install_sensu_server: true
      client_cert: "my_client_cert.pem"
      client_key: "my_client_key.pem"
      dashboard_user: "myadmin"
      dashboard_password: "mypass"
      redis_host: "my-redis-host"
      #client config
      sensu-server: "my-sensu-server.co.uk"
      sensu_server_address: "192.168.0.1"  
```

Role variables
--------------

List of variables used by the role:

```
# Variables for installation of client/server
install_sensu_server: false
install_sensu_client: true
client_cert: "client_cert.pem"
client_key: "client_key.pem"

# Common defaults
sensu_config_dir: "/etc/sensu"
sensu_ssl_dir: "/etc/sensu/ssl"

# Client defaults
sensu_server: "sensu-server.com"
sensu_server_address: "10.0.0.1"
sensu_subscriptions: "test"

# Server defaults
api_host: "localhost"
api_port: 4567
dashboard_host: "localhost"
dashboard_port: 8080
dashboard_user: "admin"
dashboard_password: "secret"
handlers_type: "pipe"
handlers_command: "true"
redis_host: "localhost"
redis_port: 6379
rabbitmq_port: 5671
rabbitmq_host: "localhost"
rabbitmq_user: "user"
rabbitmq_password: "mypass"
rabbitmq_vhost: "/sensu"
```

License
-------

MIT


Author
------

Robert Readman
