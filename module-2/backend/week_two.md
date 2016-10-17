## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR. 

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
    It is ORM - Object Relational Mapping tool and allows us to create, read, update and delete records from our database and much much more. 
    
2. What is a migration?
    A migration is a set of instructions to build a database table. 
    
3. How does a table relate to a model?
    Every line in the table is an instance of a model. 

4. What kind of methods are `belongs_to`, and `has_many`? (i.e. class or instance) Give an example.
    They are instance methods, I think. In case of cars/dealerships, every instance of dealerships has many cars, whereas every instance of cars belongs to a dealership. 
    
5. What do they allow you to do?
    They allow us to establish relationships/associations between the objects, which in turn allow grouping and calculations. In the example above, we can group cars by dealerships and calculate statistics per dealership if needed.  

6. What's the difference between agile workflow and waterfall method?
    Waterfall is a development process in which everything is pre-planned, it is process oriented and not very flexible when changes are needed to be implemented. Agile, on the other hand, is an iterative development process, where the project is divided into measurable iterations/chunks. Agile is very flexible and allows for easy change management (I studied Business Analysis before :))

7. What is the difference between `#new` and `#create`?
    New will not save, but is a good way to look up different attributes from rails console for example. Basically: new + save = create.

8. At a basic level, what does cURL allow you to do?
    I see cURL as a tool that allows to request different URLs from terminal which otherwise would be requested from the browser.  

9. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
    I might be wrong, but I see the relationship between students/teachers as many-to-many, since one student can have many teachers available and one teacher can have many students in the class. Following this logic, we will create a Teachers-Student table which would have foreign keys (student.id, teacher.id) in it. 
   
10. Define foreign key, primary key, and schema.
     Primary key is the id column value in a given table. Foreign key is a primary key from a different table which might have been added to a second table because of certain association.

11. Describe the relationship between a foreign key on one table and a primary key on another table.
     In case of cars/dealerships, the foreign key dealership.id would be placed in cars table because of one-to-many relationship between dealership and cars. 

12. What are the parts of an HTTP response?
      Method, URI, protocol, header, body. 

13. `Rack::Test` allows us to test our controllers in isolation. What are some of the methods it gives us to simulate the request/response cycle?
      The only thing I know about Rack at this point is the exchange of hash/array of data. 
      
14. Describe some techniques to make our Sinatra views more DRY. Give an example of when you would use these techniques.
      Using partial forms: I knew new.erb and show.erb are usually similar and I learned from Blogger tutorial that I can use a partial so that I do not repeat myself. 


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
3. What's the difference between agile workflow and waterfall method?
4. What can you expect from a group as you begin working together? As you continue working together?
5. What two columns does `t.timestamps null: false` create in our database?
6. What cURL flag can you use to send a `POST` request?
7. What case does JSON (and JavaScript) use for multi-word variables?
8. What case does Ruby use for multi-word variables?
9. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
10. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
11. Give an example of when you might want to store information besides ids on a join table.
12. Describe and diagram the relationship between patients and doctors.
13. Describe and diagram the relationship between museums and original_paintings.
14. What are some examples of acceptable values for the parts of an HTTP response?
15. What types of output do we want to test when we test our controllers?
16. What could you see in your code that would make you think you might want to create a partial?
17. Why might you use a helper method?
