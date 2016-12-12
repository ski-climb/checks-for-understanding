## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR. 

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
 * *ActiveRecord is the go-between from ruby to the database.  It allows us to query the database using ruby and ruby-like (ActiveRecord) methods.*
 * *It also allows us to swap out what kind of database (e.g. Postgresql, MYSQL, etc...) we're using and not change our model or migration code, although I'm not sure what kind of changes would have to be made if we swapped to a non-relational database.*
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
 * *`Team.all, Team.find, .find_by, .count, .where, .pluck, .find_each, ...`*

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
 * *`Team.find(4).name` would find the team's name*
 * *the id for the owner would be `the_owner_id = Team.find(4).owner_id` so the owner's name could be found then with:*
  * *`Owner.find(the_owner_id).name` assuming there was an `Owner` table and class.*

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
 * *`owner_name = Team.find(4).owner.name`*

3. What do they allow you to do?
 * *That addition to the `Team` class allows us ot take advantage of the ActiveRecord methods which are generated for a `belongs_to` relationship (like call `Team.first.owner`).*
7. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

```ruby 
class Student << ActiveRecord::Base
  belongs_to :teacher
end

class Teacher << ActiveRecord::Base
  has_many :students
end
```
 * *As far as the schema, the Student table would have an id, a foreign key called teacher_id, and most likely a name and maybe a school assignd student id.  The Teacher table would have an id and most likely a name.*
8. Define foreign key, primary key, and schema.
 * *A foreign key is a column on a database table that points to another row's primary key (`teacher_id` is a foreign key in the above example).*
 * *A primary key is the unique identifier for a row within a database table.  It is often an integer, but only needs to be a column o unique values (think Social Security Numbers here).*
9. Describe the relationship between a foreign key on one table and a primary key on another table.
 * * A foreign key points ot a primary key.*
10. What are the parts of an HTTP response?
* *The headers (things like the HTTP response code, say 200, what kind of response is coming back, maybe HTML, content-length in bytes, etc..) and the body (the actual HTML which was described in the headers).*
11. Describe some techniques to make our Sinatra code more DRY. Give an example of when you would use these techniques.
 * *When I think back to Bike Share, I think we could have saved a lot of time and effort if we had used partials to represent the input fields for the new and edit forms when we were doing the CRUD portions of the application.  Hmmm, and we probably should have used factories for creating test objects too.*


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
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
