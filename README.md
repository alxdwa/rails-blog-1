# rails-blog-1 #

First day of learning Rails and deploying to Heroku. Blog created following instructions on [Rails Guides - Getting Started with Rails](https://guides.rubyonrails.org/getting_started.html), and deployed on Heroku [here](https://powerful-wildwood-70939.herokuapp.com/).

Notes from today:

Create new rails app:
`rails new <filename> -d postgresql`

Change into directory:
`cd <filename>`

Create database
`rails db:create`

Migrate database
`rails db:migrate`

While inside directory, initialize Heroku:
`Heroku create`

A remote repo called 'heroku' is created. We can then use git to push our code onto the web server:
```
git add .
git commit -m "MESSAGE"
git push heroku master
```

----

I initially created rails directory/app using default sqlite3, so I had to manually change db to postgres. I followed these steps:

1. Changed Gemfile--removed sqlite3 line and added 'pg'
2. `bundle update`
3. edited database.yml file 
```
development:
  adapter: postgresql
  encoding: unicode
  database: demo_test_development
  pool: 5
  timeout: 5000

test:
  adapter: postgresql
  encoding: unicode
  database: demo_test_test
  pool: 5
  timeout: 5000
```

4. `rails db:setup`
5. `rails db:migrate`

----

Other commands run today:

if not specifying postgres as db:
`rails new <appname>`
then update gemfile sqlite line with version: 'sqlite3', '<1.4'

created a basic scaffold:
`rails g scaffold Post title:string body:text`
`rails db:migrate`

for help, and output dependent on pwd:
`rails -h`


~/CA/28mar/blog