# ruby-on-rails-review

## Getting Started

`cd simple-blog`

then `rails server`

## Some very obvious notes: 

MVC 

- Model deals with interacting with database CRUD
- Controller "controls" data between DB and views
- Views take database and serve as presentation layer.

Idea is separation of concerns.

## Key folders

/app is the main folder.

### Controllers
Every controller is going to extend app/controllers/application_controller.rb


#### Generate Controller
type `rails g controller Posts`, for ex.  This creates a Posts controller file, Posts folder inside views, posts_helper, scss, and test.  

### Views
/app/views/layouts/application.html.erb is the main layout.
`<%= yield %>` injects the specific view contents.

### Routes
/app/config/routes.rb

so `root 'posts#index'` says for the root URL, go to posts controller and get the index view (the method defined as index will return that view with the same name)

for normal routes, get post etc. e.g., `get 'about' => 'pages#about'`, goes to pages controller and gets about method.

You can type `rake routes` to show all routes for application.

### Creating functions in Ruby

`def index ... end` is the same as `function index() { ... }`

### Defining Database (SQLite, MySQL, etc.)

/config/database.yml

#### Defining models:

Good practice to use plural for controllers, singular for models.
`rails g model Post title:string body:text`, for ex.

This creates a migration file as well (in /db/migrate), but doesn't run the migration.

To run this, run `rake db:migrate`

