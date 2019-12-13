# Angular App Deploy on Heroku Steps

Sample Angular App Deploy on Heroku setps

### How to start

In order to start the deploye project:


### Create Angular App

```bash
# Clone project or Create new Project
$ git clone URL
$ cd <Project_Name>
# install the project's dependencies
$ npm install
# watches your files and uses livereload by default run `npm start` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.
$ npm start
# check application running on above URL
```

### New Account

Create new Account on [Heroku](https://id.heroku.com/login).

### Install the Heroku CLI

Download and install the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli).


### Update package file and Add Server file

```bash
# Add express npm
$ npm i express --save
```

Add `Server.js` file in same repository, Add below containt

```bash
//Install express server
const express = require('express');
const path = require('path');
 
const app = express();
 
// Serve only the static files form the dist directory
// Replace the '/dist/<to_your_project_name>'
app.use(express.static(__dirname + '/dist/my-app'));
 
app.get('*', function(req,res) {
  // Replace the '/dist/<to_your_project_name>/index.html'
  res.sendFile(path.join(__dirname + '/dist/my-app/index.html'));
});
// Start the app by listening on the default Heroku port
app.listen(process.env.PORT || 8080);

```

In `Package.json` file
Add `'postinstall':'ng build --aot --prod'` in script tag

Change in `'start'` tag value to `node server.js`

Add `"engines": {
    "node": <Node_Version>,
    "npm": <NPM_Version>
  }`


Download and install the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli).

### Heroku Process To Deploy

Open git bash(Download and install [Git](https://git-scm.com/downloads)

```bash
# Init git
$ git init
# Login to heroku
$ heroku login
# Go to existing repository or create new repository
$ cd <Project_Name>
# Point to Heroku app nam
$ heroku git:remote -a <App_Name_Heroku>
# Add files
$ git add .
# Commit files 
$ git commit -m "comment"
# Push changes and deplyed to domain
$ git push heroku master
```

### Other option also available to deploy on Heroku like connect GitHub account
