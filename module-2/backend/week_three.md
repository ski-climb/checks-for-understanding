## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?
 * *rails new my_app -d postgresql -T --skip-turbolinks --skip-spring*
2. What do Models generally inherit from in rails?
 * *ActiveRecord::Base, like so: class Horses < ActiveRecord::Base < end*
3. What do Controllers generally inherit from in a rails project?
 * *ApplicaitonController, e.g. HorsesController < ApplicationController < end*
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
 * *resources :horses, only: [:show]*
5. What rake task is useful when looking at routes, and what information does it give you?
 * `rake routes`
6. What is an example of a route helper? When would you use them?
 * *e.g.* `horses_path`* we might use them in the specs or when creating a link, e.g. link_to "Horses", horses_path*
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
 * *_url will return the full url, e.g. http://www.horseofcourse.com/horses and the _path is relative to root, so just /horses*
8. What are strong params and why are the necessary?
9. What role does `form_for` play in helping us create our forms?
10. How does `form_for` know where to submit the user's input?
11. Create a form using a `form_for` helper to create a new `Horse`. 
12. Why do we want to validate our models?
