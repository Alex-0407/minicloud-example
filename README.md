# minicloud-example
koa app integrate with minicloud+sqlite/mysql/mssql/postgres

## Clone
```js
$ git clone http://github.com/minicloud/minicloud-example
```
## Installation package
```js
$ cd minicloud-example
$ npm install 
china user中国大陆用户建议下面方式安装依赖(cnpm 详情见:http://npm.taobao.org/)
$ cnpm install
```

## Initialization database
```js
//default sqlite

$ node ./node_modules/minicloud/install.js 

//mysql

$ node ./node_modules/minicloud/install.js --config=./config-mysql.json

//mssql

$ node ./node_modules/minicloud/install.js --config=./config-mssql.json

//postgres

$ node ./node_modules/minicloud/install.js --config=./config-postgres.json
```
## Run example
```js
//default sqlite

$ node index.js

//mysql

$ node index.js --config=./config-mysql.json

//mssql

$ node index.js --config=./config-mssql.json

//postgres

$ node index.js --config=./config-postgres.json

```
## Test case
```js
//register user

curl -X POST http://127.0.0.1:8030/api/v1/users/register \
    --header "Content-Type: application/json" \
    --data "{\"name\":\"zhangsan\",\"nick\":\"xiaozhang\",\"password\":\"8k9v6n\",\"email\":\"zhangsan@minicloudjs.com\"}"

//login 

curl -X POST http://127.0.0.1:8030/api/v1/oauth2/token \
    --header "Content-Type: application/json" \
    --data "{\"name\":\"zhangsan\",\"password\":\"8k9v6n\",\"device_name\":\"test-pc\"}"

//If successful, there will be the following information output

{"token_type":"bearer","access_token":"xxxxx","expires_in":3600}

```
