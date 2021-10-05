# Deploy Chainlink nodes in K8s

Deploy Chainlink nodes with Kubernetes

## Pre-req

1. This deployment was tested on [Linode](https://www.linode.com/) and loadbalancer service created for Linode Loadbalancer - make changes to code per your cloud provider.
2. You will need a running PostgreSQL database.
3. Export the required variables below for the deployment.

| Variable | Description                                                                                                        |
| -------- | ------------------------------------------------------------------------------------------------------------------ |
| API      | <span>base64 encoded API creds: <br><code>echo -e "api_username\napi_password" &#124; base64</code></span>         |
| PWD      | <span>base64 encoded keystore password: <br><code>echo -e "keystore_pwd" &#124; base64</code></span>               |
| ETHURL   | Ethereum client websocket endpoint (from on-prem or provider infura, fiews, etc.) <br><code>wss://eth.url</code>   |
| DBURL    | Postgres connection string: <br><code>postgresql://<db_username>:<db_password>@<db_url>:<db_port>/<db_name></code> |

4. Use `envsubst` to populate required variables to K8s objects during deployment.

```
envsubst < k8s_object.yaml | kubectl apply -f -
```
