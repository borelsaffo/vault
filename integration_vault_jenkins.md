##

![image](https://github.com/borelsaffo/vault/assets/27947973/6a107ef6-a20b-4a05-8ed8-8c46717d46d6

##
![image](https://github.com/borelsaffo/vault/assets/27947973/f08166d1-cb68-4d47-894a-ff7e34ec1f6f)



### Vault dans Gitlab-ci

before_script:
  - apk add --update --no-cache ca-certificates curl
  - curl -LsO https://github.com/hashicorp/vault-plugin/releases/latest/download/vault-plugin
  - chmod +x vault-plugin

variables:
  VAULT_ADDR: "https://vault.example.com"
  VAULT_PLUGIN_DOWNLOAD_URL: "https://github.com/hashicorp/vault-plugin/releases/latest/download/vault-plugin"
  VAULT_PLUGIN_CMD: "./vault-plugin"
  VAULT_ROLE_ID: "your-role-id"
  VAULT_SECRET_ID: "your-secret-id"

script:
  - export VAULT_ADDR=$VAULT_ADDR
  - export VAULT_TOKEN=$($VAULT_PLUGIN_CMD auth gitlab --role-id=$VAULT_ROLE_ID --secret-id=$VAULT_SECRET_ID)
  - export VARIABLE_1=$($VAULT_PLUGIN_CMD read -field=variable_1 secret/path/to/variables)
  - export VARIABLE_2=$($VAULT_PLUGIN_CMD read -field=variable_2 secret/path/to/variables)
# Rest of your pipeline steps...

## End

### Vault dans un job bash

#!/bin/bash

# Retrieve the username and password from Vault
username=$(vault read -field=username secret/path/to/dockerhub)
password=$(vault read -field=password secret/path/to/dockerhub)

# Log in to hub.docker.com
docker login -u "$username" -p "$password"

# Build and push the Docker image
docker build -t your-image .
docker push your-image




##### Intégration 

To configure your Jenkins jobs to retrieve variables from Vault, you can use plugins like "HashiCorp Vault 
Plugin" or "Vault Plugin" that integrate Jenkins with Vault. Here's a general overview of the steps involved:

    Install the Vault plugin: In the Jenkins dashboard, go to "Manage Jenkins" → "Manage Plugins" → "Available" tab. 
    Search for the Vault plugin and install it.

    Configure the Vault plugin: Once the plugin is installed, go to "Manage Jenkins" → "Configure System" → "HashiCorp Vault" section.
    Add the Vault server URL, authentication method (token, AppRole, etc.), and other relevant details.

    Create a Vault token: Generate a Vault token with appropriate access policies to retrieve the desired secrets or variables.

    Configure Jenkins job: In your Jenkins job configuration, add a "Build Environment" step for the Vault plugin. 
    Provide the Vault token or authentication details, and specify the secrets/variables paths you want to retrieve from Vault.

    Use Vault variables in the job: In your Jenkins job, you can access the retrieved Vault secrets/variables as 
    environment variables. For example, you can use ${VAULT_SECRET_NAME} to refer to a specific secret retrieved from Vault.

By following these steps, your Jenkins job will authenticate with Vault, retrieve the desired secrets/variables, 
and make them available as environment variables for your job's execution.

![image](https://github.com/borelsaffo/vault/assets/27947973/fdeda03d-5cdc-4d42-97c0-5c80fb7b0655)

![image](https://github.com/borelsaffo/vault/assets/27947973/fe119eb4-c573-4a05-b26a-cdec193ad6a1)

![image](https://github.com/borelsaffo/vault/assets/27947973/b2de220b-5d27-4aaa-a7d6-8dd52b09c3db)


