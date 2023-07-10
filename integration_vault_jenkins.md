##

![image](https://github.com/borelsaffo/vault/assets/27947973/6a107ef6-a20b-4a05-8ed8-8c46717d46d6

##
![image](https://github.com/borelsaffo/vault/assets/27947973/f08166d1-cb68-4d47-894a-ff7e34ec1f6f)



### Vault dans Gitlab-ci
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


