# Basic-BE-Setup
Basic Backend Setup

This is a loose guide for setting up a backend for React

### Minimal setup for testing if the BE works
1. Download repo from Github   
2. If the repo doesn't have a package.json file in it, you need to run ```npm init```.  This will install a package.json file.
3. Determin which packages you'll need (e.g., sqlite, express, etc) and install them.    
4. Create a index.js file.  Require the server.js file and setup your server listener
5. Create a server.js file.  Require express, setup an express server, express.json() for parsing content, a test endpoint to make sure the server is working, and make sure to export it so the index.js file has access to it.    
6. If it doesn't work, recheck your code.    
7. If it works, install some other middleware if you haven't, and set it up in the server.js file.  For instance, cors, helmet, a logger, etc.
8. Test again to make sure the server is running.

### Database
1. Make sure sqlite and knex are installed.  You can see in the package.json
2. Starting with knex, at the terminal type ```npx knex init```.  This will create a knexfile.js.    
3. In knexfile.js, the minamal setup should have

```  
development : {
         client: 'sqlite3',
         useNullAsDefault: true
        connection” {
              filename: './data/rolex.db3'
       },
}
```
4. NOTE!!!! When you get into deploying the website (e.g., heroku), the basic knexfile.js above will change quite a bit. 
5. When this is setup properly, at the terminal type 
```npx knex migrate:make whatever_you_want_to_call_your_table```
6. This will create a migrations folder and a data folder with the link to your db3 file.  In my example above it would be rolex.db3.    

### Migrations
1. Setup your migrations.  I think you have enough examples already to draw upon to see how to do this.
2. When your migrations are setup, at the terminal type ```npx knex migrate:latest```
3. To undo the migrations type ```npx knex migrate:rollback```

### Seeds
1. At the terminal type ```npx  knex seed:make  001-whatever_you_want_to_call_your_seeds```.  Be sure to number them.
2. Again, I think you have enough examples to draw upon to see how the seeds are made.

### Config file
1. Create a utils folder, and inside that create your link to the database.  It's the one that looks like this.    
```
const knex = require('knex');

const configOptions = require('../knexfile').development;

module.exports = knex(configOptions);
````


