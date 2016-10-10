## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.
    "GET"- instructs the web app to display the content matching that specific URL
    "HEAD" - same as get except the server must not dispaly anything
    "PUT"/"PATCH" - instructs to create or update the thing specified by the URL
    "POST"- instructs the servers to repeat processing
    "DELETE" - instructs to delete that thing specified by the URL
    
2. What is Sinatra?
    Sinatra is a Ruby web-development framework that is ideal for applications of smaller size. 
    
4. What is MVC?
    It is the conventional structure of the web application, including models-views-controllers
    
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
    We do so in order to make our code more readable to others. Also, we learn beautiful and graceful solutions for specific to specific       problems. 
    
6. What types of variables are accessible in our view templates without explicitly passing them?
    Instance variables

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed`?

  ```ruby
  get '/horses' do
    @count = 1
    erb :index, locals: {name: 'Mr. Ed'}
  end
  ```

9. What's the purpose of ERB?
    Embedded Ruby is, in my opinion, some king of bridge between html and Ruby. It is useful when genertating Web pages with embedded Ruby     content. 
    
10. Why do I need a development AND test database?
      Because we do not want to contaminate the development database with fake data we created for test database. 

11. What's responsive design?
      Responsive design allows the web-page to get bigger or smaller in size depending on the window size it is being viewed in. 
  
12. What is CRUD and why is it important?
      Create, Read, Update and Delete functions are important because they allow all possible record manipulations in our databases.

13. What does HTTP stand for? 
      Hypertext Transfer Protocol 

14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
      <- evaluates Ruby but does not display the output >
      <= evaluates Ruby and displays the output >

15. What's an ORM?
      Object-Relational Mapping lets you query and manipulate the database using object-oriented programming. It is usually a library,           like ActiveRecord in Ruby.  

16. What's the most commonly used ORM?
      I only know ActiveRecord. 

17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
      
    To see all restaurants: 
    
      get '/restaurants' do 
        @restaurants = Restaurants.all
        erb: index
      end 
      
    To see one restaurant: 
    
      get '/restaurants/:id' do |id|
        @restaurant = Restaurant.find((id)
        erb: show
      end 
      
    To pull up the form to enter a new restaurant: 
    
      get '/restaurant/new' do 
        erb: new  
      end 
    
    To create the new restaurant: 
    
      post '/restaurants' do 
        Restaurant.create(params[:restaurant])
        redirect '/restaurants'
      end 
      
    To pull up the form to edit a created restaurant:   
      
      get '/restaurants/:id/edit' do |id|
        @restaurant = Restaurant.find(id)
      end 
      
    To actually update the restaurant: 
    
      put '/restaurants/:id' do |id|
        Restaurant.update(params[:restaurant], id)
        redirect '/restaurants/:id'
      end 
      
    To delete a restaurant: 
    
      delete '/restaurants/:id' do |id| 
        Restaurant.delete(id)
      end 
      

18. What's a migration? 
      A migration allows to use Ruby to define changes to database schema. 

19. When you create a migration, does it automatically modify your database?
      No, you should update the migration file and actually migrate it afterwards with this command: rake db:migrate

20. How does a model relate to a database?
      Usually every line in the database table is an instance of the model. 
