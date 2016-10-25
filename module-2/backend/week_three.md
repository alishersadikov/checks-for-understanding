## Week Three Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What are the 3 main features in an ERD? ERD is a good tool to visualize the schema of the database.

It shows what columns/attributes there are in tables/models. More importantly, it shows primary keys and foreign keys and therefore is a good indicator of one-to-one and/or one-to-many relationships. Finally, it demonstrates joint tables which stand for many-to-many relationsihps. 

2. Create an ERD for the following database: Restaurants, Customers, Items, Ingredients, Beverages, Orders, Vendors.

    restaurants: id, name, address, phone_number
    customers:   id, name, phone_number 
      
    restaurant-customers: id, restaurant_id, customer_id
    
    ingredients: id, title, item_id
    items:       id, title, order_id
    beverages:   id, title, type, order_id
    orders:      id, customer_id
    
    vendors:     id, name, phone_number, email
    
    restaurant-vendors: id, restaurant_id, vendor_id
    
  Sorry, didn't know how to draw in markdown. In other words, a customer can go to many restaurants, and a restaurant has many             customers. An ingredient belongs to an item, an item and a beverage both belong to an order. A vendor has many restaurants it delivers   goods/services to, and a restaurant has many vendors.
    

3. What is the entry at the command line to create a new rails app?
  
  rail new myapp

4. What do Models generally inherit from in rails?
  
  ActiveRecord::Base

5. What do Controllers generally inherit from in a rails project?

  ApplicationController
  
6. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

  get '/horses/:id', to: 'horses#show' 
  Alternatively: resources: horses, only: [:show]
  
7. What rake task is useful when looking at routes, and what information does it give you?

  rake routes shows all routes available within the app
  
8. What is an example of a route helper? When would you use them?

  In the example above, horse_path would be a route helper that is used to redirect to that specific horse's show page. 
  
9. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
  
 '_url' returns absolute path (with reference to root), '_path' returns relative path (with reference to current dir)

10. What are strong params and why are the necessary?

  Strong params are necessary because we don't want to save attributes in the params hash that are not to be stored in the instance of the relevant object. 
  
11. What role does `form_for` play in helping us create our forms?

  It renders the form for what comes afterwards as in form_for('instance_of_object') and is useful in storing the data in the relevant attributes of this specific instance.
  
12. How does `form_for` know where to submit the user's input?
  
  It knows it as long as we specify it as form_for('instance_of_object').

13. Create a form using a `form_for` helper to create a new `Horse`. 

  Assuming we have name and age attributes for Horse model and send @horse = Horse.new() from our controller to view:

  <%= form_for @horse do |f| %>
  <%= f.label: name %>
  <%= f.text_field: name %>
  <%= f.label: age %>
  <%= f.number_field: age %>

14. Why do we want to validate our models?

  We want to validate our models to make sure we do not create instances with missing attributes that are vital for that model. Sometimes we want to validate uniquenesss in our models because we do not want to create instances with identical attributes. 
