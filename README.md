# Wazuh Docker Agent

## Environment Variables

The following environment variables are allowed:
* `WAZUH_AGENT_GROUP` : Used to define the group of the agent.
* `WAZUH_AGENT_PREFIX` : Used to define the name prefix of the agent. The result will be: `{PREFIX}-{HOSTNAME}`. If not set only the `{HOSTNAME}` will be used.
* `WAZUH_AGENT_PASSWORD` : Used to define the registration password.
* `WAZUH_MANAGER_IP` : Used to define the Wazuh Manager IP. Default: `wazuh-manager`.

## Usage:

### Create Docker image

```
git clone https://github.com/fhielpos/wazuh-docker-agent.git
cd wazuh-docker-agent
docker build -t wazuh-agent:4.1.4 .
```

### Run the Docker image

```
docker run -d \
--env WAZUH_MANAGER_IP='MANAGER_IP' \
--name=wazuh-agent \
wazuh-agent:4.1.4
```

**Note** : If no `WAZUH_MANAGER_IP` is defined, then it is needed to define the IP with: `--add-host=wazuh-manager:<MANAGER_IP>`
