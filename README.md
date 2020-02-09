# Basic-BE-Setup
Basic Backend Setup

This is a loose guide for setting up a backend for React

### Minimal setup for testing the BE works
1. Download repo from Github   
2. If the repo doesn't have a package.json file in it, you need to run ```npm init```.  This will install a package.json file.
3. Determin which packages you'll need (e.g., sqlite, express, etc) and install them.    
4. Create a index.js file.  Require the server.js file and setup your server listener
5. Create a server.js file.  Require express, setup an express server, express.json() for parsing content, a test endpoint to make sure the server is working, and make sure to export it so the index.js file has access to it.    
6. If it doesn't work, recheck your code.    
7. If it works, install some other middleware if you haven't, and set it up in the server.js file.  For instance, cors, helmet, a logger, etc.
8. Test again to make sure it works. 

