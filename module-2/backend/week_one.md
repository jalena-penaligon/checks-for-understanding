## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
Get - Reads
Post - Creates
Put - Updates (partial)
Patch - Updates (all)
Delete - Destroys

2. What is Sinatra?
Sinatra is a DSL that allows you to create web applications.

3. What is MVC?
An organizational strategy where you have a Model, View and Controller. The Controller is the liaison between the Model and the View. The Controller is the traffic cop. Its responsibility is to get information from the model, and distribute it to the view. The Model's responsibility is to interact with the database and performing any calculations or data logic. The view is responsible for page layout with HTML, and any presentation logic.

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
We follow RESTful conventions because of their readability. It allows others to step into our code and quickly understand what the intention of each route is.

5. What types of variables are accessible in our view templates without explicitly passing them?
Local variables

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
```ruby
get '/horses' do
  @count = 1
  name = "Mr. Ed"
  erb :index
end
```

8. What's the purpose of ERB?
It allows us to embed Ruby code into HTML.

9. Why do I need a development AND test database?
Development databases may be continuously changing, so it's hard to make assertions on their contents. Additionally development databases could hold live data, so you may not want to put test data in the mix.

10. What is CRUD and why is it important?
Create
Read
Update
Destroy
It's important that our applications have the ability to handle all 4 items within our database.

11. What does HTTP stand for?
Hypertext transfer protocol.

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
<%= ruby =>
<% ruby %>
The first way will print the return value, whereas the second one will not.

13. What's an ORM? What does it do?
An Object Relational Mapper. It helps us communicate between databases and Object Oriented Classes.

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?
ActiveRecord

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
Update - Update item
New - Display form to create new item
Delete - Delete item
Index - Display all items
Create - Create new item in database
Edit - Display form to edit item
Show - Show info on item

16. What's a migration?
A migration can create a table, or update schema of the table.

17. When you create a migration, does it automatically modify your database?
You have to both create and run a migration before it will have any impact on your database schema. If you add a column, data will not automatically be added there for existing data.

18. How does a model relate to a database?
A model interacts with the database and performs any necessary calculations.

19. What is the difference between `#new` and `#create`?
New displays an input area to create a new item. Upon submission, that item is created in the database.

20. Given a table named `animals`, What is the SQL query that will return all info from that table?
    `id     name        number_of_legs
    -----   ------      --------------
      1     panda       4
      2     giraffe     4
      3     whale       0
      4     bird        2
    `
SELECT * FROM animals

21. Using the same table, What is the SQL query that will return only the animals that has 4 legs?
SELECT * FROM animals WHERE number_of_legs = '4'

### Review Questions:  
22. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
films = CSV.read(films.csv, {headers:true, header_converters: :symbol })
films.each do |film|
  Film.new(title: film[:title], description: film[:description])
end

23. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?
activities[:hiking][:supplies] << "granola bar"


24. What are the 4 Principles of OOP? Give a one sentence explanation of each.
Encapsulation: Hides data by restricting access to certain methods
Abstraction: You don't need to know what's under the hood to drive a car
Inheritance: Classes can inherit attributes or behaviors from another class or module.
Polymorphism: Methods can look different, but do the same thing.

### Self Assessment:
Choose One: (erase the others)
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
