## Day 23 - 14 Oct 2020

### Connecting Applications to a Database

* We use the node module *pg* to connect a Node/Express application to a Postgres database, for example:

```javascript
const { Client } = require('pg');

const connection = new Client({
  user: process.env.DATABASE_USER,
  host: process.env.DATABASE_HOST,
  database: process.env.DATABASE_NAME
});
```

* Best practices is to put database connection in a separate file. Being modular means it's easy to swap databases if necessary

### Ensuring No Duplicate DB Connections

* Create only a single database connection, in one file. (If you require the database connection object in multiple files, it could create multiple connections to the same database, which is not good for performance)
* If you need a database connection in multiple files, have the database object passed into all functions it's needed in as an argument
* Or better yet, create a factory function that returns functions with the single database as an argument. For example:

``` javascript

// in db-helpers.js 
const factoryFunc = (db) => {
  const function1 = () => {
    return db.query(/* Whatever query */);
  }
  const function2 = () => {
    return db.query(/* Another query */);
  }

  return {
    function1, 
    function2
  };
};

// in main.js
const db = /* The One DB Connection To Rule Them All */
const dbHelpers = require('./db-helpers')(db);
```

### Security

* Do not put database credentials in a git-exposed file
* The node package *dotenv* can be used to take credentials from a separate file and save them into process.env
* Always sanitize any input going into a database (otherwise SQL injection is possible)