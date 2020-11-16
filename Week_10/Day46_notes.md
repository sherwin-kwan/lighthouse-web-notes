# Day 46 - Rails Tutorial

## Random Rails Tips

* Doing *resource: :farm* will give you all the routes of *resources: :farms* without the ":id" routes
* You can do custom, non-REST routes like "get '/pages', to 'pages#about'
* a single "Pages" controller is usually a good way to get static pages like "About" set up
* Never edit schema.rb directly. You need to write a migration to create/change/delete tables
* If you make a mistake in a migration, make a new migration to fix the error. (Or if you're 100% sure no one has pulled the error, roll back and fix the migration)
* By default, Rails does server-side rendering. If you want to use a separate front-end framework like React, you can instead create a Rails app with:

```
rails new my_api --api
```
* Or to modify an existing Rails app to be API-only, put this in the Application class:
```
config.api_only = true
```
* This will generate a Rails app without "views". You will only have the ActiveRecord/models part of the app
* Then, when you need to send data to the front end, do:
```
render json: @object_name
```
This will send JSON in response to any HTTP request at that route