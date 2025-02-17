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

- `./env_vars/.POSTGRES_PASSWORD` - Change the password for the Postgres database
- `./.env` - Change the following parameters:
    * `ZBX_VERSION` - Zabbix version you would like to use, for example, 7.0
    * `FQDN` - Fully Qualified Domain Name for the Zabbix Frontend
    * `SERVICE_NAME` - Name of the service, for example, zabbix
    * `LE_EMAIL` - Email for Let's Encrypt
    * `WG_BASIC_AUTH` - Basic Auth for the Zabbix Web Service (view .env file for more information)

    * Optional / Dynamic Parameters:
      * `CF_EMAIL` - Cloudflare email. If you are not using Cloudflare, remove the Cloudflare settings from the traefik service in the `docker-compose.yml` file
      * `CF_API_KEY` - Cloudflare API key. If you are not using Cloudflare, remove the Cloudflare settings from the traefik service in the `docker-compose.yml` file

The `./env_vars` directory contains the environment variables for the Zabbix containers. You can edit these files to change the default settings for the Zabbix containers.

## Usage

To start the Zabbix setup, run the following command:

```bash
docker-compose up -d
```
