## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?
 * *A cookie is a piece of information that the client browser has saved and is generally set by the server.*
* What’s the difference between a session and a cookie?
 * *A session operates in much the same way as a cookie but the information is hashed by the server.*
* What’s a flash and when do you want to use flashes?
 * *A flash is a cookie that expires.*
* Why do people say “HTTP is stateless”?
 * *Because each request from the client to the server is handled as though it is a new request - with the server having no prior knowledge of any communication that might have occurred between the client and the server.*
* What’s authentication? Explain.
 * *Authentication is the process of verifying that you are, indeed, who you claim to be.*
* What’s the difference between authentication and authorization?
 * *Authorization is determining what you are allowed to do.  The difference is that, once I have authenticated that I am a logged in user, I might be authorized to see my own profile page, but not anyone else's nor an admin's dashboard.*
* What’s a before filter?
 * *A before action is a method that will run prior to the other actions in the controller (I think before_actions are only in the controllers).*
* How do we keep track of a user once they’ve logged in?
 * *We store their user id in the session.*
* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
 * *One reason to namespace a resource might be, say, because only admins can see a list of all users.  Then the users index might be namespaced under admin.  And by namespacing that way, you could restrict access to that (potentially sensitive list of users) by only allowing admins to access that view.  One reason to nest a resource might be if there is a one to many relationship.  For example, if one team has many players.  Then it might make sense to nest players under a team so that it would be straightforward to do something like view all players for a particular team.*
* At a high level, what tools can you use to implement authorization? How would you use them?
 * *At the controller level, I would most likely use methods that look for a current_user?, or current_admin? to determine whether a user should have access to a particular resource/view/controller/etc...
* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
 * *An enum is one way to declare a custom set of attributes for a model, and ActiveRecord then provides some convenience methods that allow us to easily set and query an object about those custom attributes.*
* What are some strategies you can use to keep your views DRY?
 * *Putting forms in partials help to eliminate duplicated code (like new and edit).  Adding things like navigation, errors and flash notices to the layout helps.  And even putting often used buttons in partials can DRY up the code.*
