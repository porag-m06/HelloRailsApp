# HelloRailsApp
Let's create an entire usable project with one simple line: 
- `rails new Project` [Sets SQLite3 as the default DB]

## But first,
Let's check to make sure that our system has the proper prerequisites installed. 
These include:
- Ruby (`ruby --version`) 
- SQLite3 (`sqlite3 --version`) [SQLite3 Website](https://www.sqlite.org/index.html)
[And we can use postgreSQL instead as well]

And also check if rails is installed on our machine already by running: 
- `rails --version`

If not, let's install rails & then we will also choose postgreSQL as our default DB during the creation of our first app.

To install rails & check version: 
- `gem install rails`
- and check again by running `rails --version`

To set `postgresql` as the default database instead of SQLite3
- `rails new ProjectName --database=postgresql`

This will create a Rails application called `ProjectName` in a directory called ProjectName. Now go to
- `cd ProjectName`

and install all the gem dependencies that are already mentioned in `Gemfile` using 
- `bundle install`

To Run/ Server the project: 
- `rails server` or, 
- `bin/rails server` or `bin/rails s`
- For windows run `ruby bin\rails server`

This will start up `Puma`, a web server distributed with Rails by default. To see your application in action, visit http://localhost:3000/ in your browser!
PS: we can press Ctrl-C to stop the server.

#### Play with your first Rails website

After checking to make sure our Rails project is being served to the browser (http://localhost:3000/), there are a few things that need to be changed in order to set the display to let us view what we want.  

- Let's use Rails' `generators` (known as scaffolding) to automagically make the files we need. For this you will do `rails generate controller Pages hello` in your shell, look at the example:
  ```
  $> rails generate controller Pages hello

      create  app/controllers/pages_controller.rb
       route  get 'pages/hello'
      invoke  erb
      create    app/views/pages
      create    app/views/pages/hello.html.erb
      invoke  test_unit
      create    test/controllers/pages_controller_test.rb
      invoke  helper
      create    app/helpers/pages_helper.rb
      invoke    test_unit
  ```
- Looking at the output of the command you will see all the generated things, but for now you only need to focus on one `app/views/pages/hello.html.erb`. You will put your HTML in this one.
- Open the file `app/views/pages/hello.html.erb` and add an `h1` element saying `"Hello world"`.
- Open http://localhost:3000/pages/hello in your browser. You should see your "Hello world" message.
- In `config/routes.rb` replace `get 'pages#hello'` with `root 'pages#hello'`
- Revisit http://localhost:3000/ and see your changes in action. Now your "Hello world" page should be displayed as the main page.

## Rails Naming Convension
<div align="center">
  <img src="./railsNamingConvension.png" alt="logo" width="auto"  height="auto" />
  <br/>
</div>