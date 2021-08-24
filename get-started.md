# Get Started

## Infrastructure

### Proxmox
Kubernox actually work only on Proxmox host, in the future we planify to add other .... provider.

### pfSense
It's the solution we choose for documentation and our developement platform.
It's not require, you can manage your own firewall or without firewall.

## Deploy Kubernox

### Kubernox CLI

#### Basic configuration

##### Kubernox Configuration (Required)

```yaml
kubernox:
    domain: my.domain.dot
    ui_port_expose: 7777
```
##### Proxmox Configuration (Required)

To deploy cluster to proxmox, kubernox required access token from Proxmox host.

The proxmox configuration look like this.

```yaml
proxmox:
    host: https://proxmox.mydomain:port
    username: kubernox
    password: kubernox
    access_token: kubernox
    token_id: kubernox
    auth_type: pam
```

```
host: https://proxmox.mydomain:port => The ip or domain for access Proxmox host, port it's mandatory.
```

```
username: kubernox => The username for access Proxmox host.
```

```
password: kubernox => The username for access Proxmox host.
```

```
access_token: kubernox => The username for access Proxmox host.
```

```
token_id: kubernox => The username for access Proxmox host.
```

```
auth_type: pam => The username for access Proxmox host.
```

##### PostgreSql Configuration

Kubernox store data in database, we choise to use postgresql as provider.
If you use Kubernox CLI, you can keep default value to deploy.

```yaml
postgre:
    host: kubernox_db
    username: kubernox
    password: kubernoxDbPassword@0123
    db_name: kubernox
    storage: db_data
```

##### RabbitMQ Configuration

Kubernox use RabbitMQ to communicate between service and workers.
If you use Kubernox CLI, you can keep default value to deploy.

```yaml
rabbitmq:
    host: kubernox_queue
    username: kubernox
    password: kubernoxRabbitMqPassword0123
    virtualhost: /
    port: 5672
```

##### Redis Configuration

Kubernox use Redis to store dymanic domain routing by traefik.
If you use Kubernox CLI, you can keep default value to deploy.

```yaml
redis:
    host: kubernox_cache
    password: kubernoxRedisPassword@0123
```

##### Prometheus Configuration

```yaml
prometheus:
    path: prometheus.yml
```

##### Traefik Configuration

```yaml
traefik:
    path: traefik.yml
    letsencrypt_providers:
        GANDIV5_API_KEY: xxxxxxxxxxxxxxxx
```

##### Full Configuration
```yaml
#################################################################
#                                                               #
#     ____  __.    ___.                                         #
#    |    |/ _|__ _\_ |__   ___________  ____   _______  ___    #
#    |      < |  |  \ __ \_/ __ \_  __ \/    \ /  _ \  \/  /    #
#    |    |  \|  |  / \_\ \  ___/|  | \/   |  (  <_> >    <     #
#    |____|__ \____/|___  /\___  >__|  |___|  /\____/__/\_ \    #
#            \/         \/     \/           \/            \/    #
#                                                               #
#          Created by David Gilson & Patrick Grasseels          #
#                                                               #
#################################################################

# Github : https://github.com/wetry-homelab/kubernox

# Configure Proxmox Host
proxmox:
    # No default value, custom value required
    # Values acceptable : xx.xx.xx.xx:port / proxmox.mydomain:port 
    host: https://proxmox.mydomain:port
    # Default value : kubernox
    username: kubernox
    # Default value : kubernox
    password: kubernox
    # No default value, custom value required
    access_token: kubernox
    # No default value, custom value required
    token_id: kubernox
    # Default value : pam
    # Possible values : pam / pem
    auth_type: pam

# Configure database provider
# Actually only Postgre is supported
# If nothing is configured, provider deploy own Postgre container
postgre:
    # Default value : kubernox_db
    host: kubernox_db
    # Default value : kubernox
    username: kubernox
    # Default value : kubernoxDbPassword@0123
    password: kubernoxDbPassword@0123
    # Default value : kubernox
    db_name: kubernox
    # Default value : db_data
    storage: db_data

# Configure queue provider
# Actually only RabbitMQ is supported
# If nothing is configured, provider deploy own RabbitMQ container
rabbitmq:
    # Default value : kubernox_queue
    host: kubernox_queue
    # Default value : kubernox
    username: kubernox
    # Default value : kubernoxRabbitMqPassword@0123
    password: kubernoxRabbitMqPassword0123
    # Default value : /
    virtualhost: /
    # Default value : 5672
    port: 5672

# Configure cache provider
# Actually only Redis is supported
# If nothing is configured, provider deploy own Redis container
redis:
    # Default value : kubernox-db
    host: kubernox_cache
    # Default value : kubernox
    password: kubernoxRedisPassword@0123

# Configure cache provider
prometheus:
    # Default value : prometheus.yml
    path: /home/tech/prometheus.yml

# Configure traefik provider
traefik:
    path: /home/tech/traefik.yml
    letsencrypt_providers:
        GANDIV5_API_KEY: 6BRQMprek9288sSA55C9bhsa

kubernox:
    domain: my.domain.dot
    ui_port_expose: 7777
```

### Kubernox Self Deploy
Lorem ipsum dolor sit amet, anim eiusmod labore excepteur pariatur magna excepteur eiusmod aute consectetur pariatur consectetur veniam exercitation commodo sunt ullamco adipisicing nisi in irure laboris magna exercitation aliquip ullamco amet incididunt sit aute consequat dolore officia in dolor irure deserunt nisi occaecat laboris labore dolore nulla amet dolor proident mollit exercitation pariatur veniam in excepteur culpa pariatur cupidatat reprehenderit velit officia magna proident sint dolore velit cupidatat et eiusmod eiusmod laborum adipisicing ut in fugiat ut tempor eiusmod exercitation laboris ad velit deserunt

Lorem ipsum dolor sit amet, anim eiusmod labore excepteur pariatur magna excepteur eiusmod aute consectetur pariatur consectetur veniam exercitation commodo sunt ullamco adipisicing nisi in irure laboris magna exercitation aliquip ullamco amet incididunt sit aute consequat dolore officia in dolor irure deserunt nisi occaecat laboris labore dolore nulla amet dolor proident mollit exercitation pariatur veniam in excepteur culpa pariatur cupidatat reprehenderit velit officia magna proident sint dolore velit cupidatat et eiusmod eiusmod laborum adipisicing ut in fugiat ut tempor eiusmod exercitation laboris ad velit deserunt
