# Lab 

## Objective
Understand how to make and use Laravel controller,  know how to make migration and seeder files and also learn about how to use artisan command for them.

## Scenario
We will make a simple home management system. In this system, user can view list of homes, create a new home, and view a specific home information.

## Tasks
- A migration file `create_homes_table` has followings fields, you need to decide their types:
    - id (primary key and auto increment)
    - unit_number (optional, can be null)
    - address_number (required)
    - street_name (required)
    - city (required)
    - province (required)
    - postal_code (required)
- A seeder `HomeSeeder` should create 100 records test data.
    - Self learning - read [here](https://laravel.com/docs/9.x/seeding)
- A controller `HomeController` has following actions:
    - index: Show a couple of home
    - create: show a form to let user to create a home
    - Store: store the home form submission and save it into database.
    - show: show a given home details
- A few routes should match above controller actions
    - GET - /homes - index
    - GET - /homes/create - create
    - POST - /homes - store
    - GET - /homes/{id} - show

Show me when you completed the lab.

Last udpate: Oct 5,2022
