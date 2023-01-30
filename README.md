# Coffee suppliers sample app

## Summary
This is a simple CRUD app built with Express.


```
git clone https://github.com/otammato/CRUD_WebApp_NodeJS_AWS_RDS_MySql.git
```

```
cd CRUD_WebApp_NodeJS_AWS_RDS_MySql/
```

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

nvm install node

nvm install --lts
nvm install 10.16.0

npm install express
```
```
# replace the endpoint with yours:

mysql -h database-2.c9rglxpvlls0.us-east-1.rds.amazonaws.com -P 3306 -u admin -p

mysql -h database-2.c9rglxpvlls0.us-east-1.rds.amazonaws.com -u admin -p  COFFEE < my_sql.sql

```


```
sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-ports 3000

sudo iptables -t nat -L 

```

```
node index.js 
```


## Running locally

### 1. Build the local Db
```sql
create DATABASE coffee;
use coffee;
create table suppliers(
  id INT NOT NULL AUTO_INCREMENT,
  name VARCHAR(255) NOT NULL,
  address VARCHAR(255) NOT NULL,
  city VARCHAR(255) NOT NULL,
  state VARCHAR(255) NOT NULL,
  email VARCHAR(255) NOT NULL,
  phone VARCHAR(100) NOT NULL,
  PRIMARY KEY ( id )
);
```

### 2. Install and run the server
```zsh
npm install

# define your db vars at start
APP_DB_HOST=localhost \
APP_DB_USER=root \
APP_DB_PASSWORD="" \
APP_DB_NAME=coffee \
npm start
```
If you do not set the env vars when starting the app the values 
from `app/config/config.js` will be used
