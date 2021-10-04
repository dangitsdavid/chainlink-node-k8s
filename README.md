# Deploy Chainlink nodes in K8s

## Pre-req

1. You will need a already running PostgreSQL database.
2. Export variables required for the deployment and using `envsubst` to populate those variables.

| Variable | Description                                                                                                        |
| -------- | ------------------------------------------------------------------------------------------------------------------ |
| API      | <span>base64 encoded API creds: <br><code>echo -e "api_username\napi_password" &#124; base64</code></span>         |
| PWD      | <span>base64 encoded keystore password: <br><code>echo -e "keystore_pwd" &#124; base64</code></span>               |
| ETHURL   | Ethereum client websocket endpoint (from on-prem or provider infura, fiews, etc.) <br><code>wss://eth.url</code>   |
| DBURL    | Postgres connection string: <br><code>postgresql://<db_username>:<db_password>@<db_url>:<db_port>/<db_name></code> |
