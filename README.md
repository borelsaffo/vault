# vault

si pas de TLS activé : 
![image](https://github.com/borelsaffo/vault/assets/27947973/ce941397-62d7-4750-93bc-46fee35026a2)

Démarrage de vault : 
![image](https://github.com/borelsaffo/vault/assets/27947973/5a4f365d-7e21-42ae-a454-087c3ffe8d24)

Initialisation de vault :  vault operator init
![image](https://github.com/borelsaffo/vault/assets/27947973/77193390-650c-4021-ab0f-a0835d5101a6)
Unseal Key 1: J19Cxb2WWTCJL284+IO04SVDDV+CSJk8t4dYbNddxg7C
Unseal Key 2: XVqeds4YGOrgX4jNmLsjN0mMGBOcjQZ08+/5avuFovaS
Unseal Key 3: zkTYCYCbXMhzQn/uI065mJshfT4hO70dpd7DudVN2E2w
Unseal Key 4: IzYwunS50Ki5IOJiJ/iSfsg9R6xnOECo/aWTrd35+Gqd
Unseal Key 5: 120GHtfuPAxEXKNeRqqmMxQjQNinb90CgEDN21mqhUNd

Initial Root Token: s.CfjUrqPbbzURU1OFyuN5dnc8

Vault initialized with 5 key shares and a key threshold of 3. Please securely
distribute the key shares printed above. When the Vault is re-sealed,
restarted, or stopped, you must supply at least 3 of these keys to unseal it
before it can start servicing requests.

Vault does not store the generated master key. Without at least 3 keys to
reconstruct the master key, Vault will remain permanently sealed!

It is possible to generate new unseal keys, provided you have a quorum of
existing unseal keys shares. See "vault operator rekey" for more information.
Les log correspondant a l'initialisation : 
![image](https://github.com/borelsaffo/vault/assets/27947973/3e973eb5-ae6d-4d58-9362-0056026c93b4)


