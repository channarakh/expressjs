#Init Project
npm install express-generator -g
express -h
express --view=ejs myapp
cd myapp
npm install

DEBUG=myapp:* npm start
set DEBUG=myapp:* & npm start

#Running app on port 1333 via command line
PORT=1333 npm start

#Running app using PM2
npm install pm2@laster -g
 1. Running on port 1333 with name exjs-classified
	PORT=1333 pm2 start npm --name "exjs-classified" -- start
 1. Running on default port which is 3000 with name exjs-classified and watching changed file
	pm2 start npm --name "exjs-classified" --watch  -- start
 1. Running on port 1333 with name extjs-classified and watching changed file
	PORT=1333 pm2 start npm --name "exjs-classified" --watch  -- start

#Default 
Application is running on port 3000 defined in bin/www

#PM2 Usage
1. PM2 list
1. PM2 delete all | appName
1. PM2 log
1. PM2 flush

#Install knex and init its configuration
npm install knex --save
node node_modules/knex/bin/cli.js init

#Use express-pretty
npm install express-prettify
http://localhost:3000/db?pretty
curl http://localhost:3000/db?pretty

#Knexjs migration and seeding
Reference: 
  1 - https://knexjs.org/#Migrations-CLI
  2 - https://knexjs.org/#Migrations
  3 - https://knexjs.org/#Schema-defaultTo 
npm install knex -g
knex init

//migration
knex migrate:make create_users_table //will create file in migrations folder
knex migrate:latest  //to execute migrate and create db.sqlite if not exists 

//migration add column
knex migrate:make add_fullname_to_users
knex migrate:latest //to 

//Seeding your database
knex seed:make 01_users
knex seed:make 02_tasks
knex seed:run //to execute seeding

#View sqlite via Command
Reference: https://www.sqlite.org/cli.html

sqlite3 db.sqlite
.help
.tables //show all tables
.quit //to exit the sqlite

.separator ", "
.width 12 6
.header off | on
.mode list | line | column | quote
select * from users; //to select all records from users table
