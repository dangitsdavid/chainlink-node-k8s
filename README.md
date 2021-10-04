# Deploy Chainlink nodes in K8s

## Pre-req

1. You will need a already running PostgreSQL database.
2. Export variables required for the deployment and using `envsubst` to populate those variables.

| Variable | Description                                                                                       |
| -------- | ------------------------------------------------------------------------------------------------- |
| API      | base64 encoded API creds: \n `echo -e "api_username\napi_password" <span>&#124;</span> base64`    |
| PWD      | base64 encoded keystore password: \n `echo -e "keystore_pwd" <span>&#124;</span> base64`          |
| ETHURL   | Ethereum client websocket endpoint (wss://eth.url - from on-prem or provider infura, fiews, etc.) |
| DBURL    | Postgres connection string: \n postgresql://<username>:<password>@<db_url>:<db_port>/<db_name>    |
