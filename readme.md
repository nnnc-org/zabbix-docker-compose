# Zabbix Docker Compose Setup

This is a simple docker-compose setup for Zabbix. It includes the following containers:
* [Zabbix Server](https://www.zabbix.com/documentation/current/en/manual/concepts/server)
* [Zabbix Frontend](https://www.zabbix.com/documentation/7.0/en/manual/web_interface?hl=Web%2Cinterface%2Cweb)
* Zabbix Database (Postgres)
* [Zabbix Agent](https://www.zabbix.com/documentation/7.0/en/manual/concepts/agent2)
* Zabbix SNMP Traps
* [Zabbix Web Service](https://www.zabbix.com/documentation/current/en/manual/concepts/web_service)

## Changes

Please edit the following:

### Env Variables
* `env_vars/.env_web`
    * `ZBX_SERVER_NAME=Example Org Monitoring`
* `env_vars/.env_agent`
    * `ZBX_HOSTNAME=example`
* `env_vars/.POSTGRES_PASSWORD`


### Docker-compose

In the docker-compose file, please edit the following line:

```yaml
# Under services
  zabbix-web-nginx-pgsql:
    ...
    labels:
      traefik.http.routers.zabbix.rule: "Host(`monitor.exapmle.org`)"
...
  traefik:
    ...
    environment:
      - CLOUDFLARE_EMAIL=test@example.org
      - CLOUDFLARE_DNS_API_TOKEN=XXXXX
```