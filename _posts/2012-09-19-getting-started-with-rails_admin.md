---
layout: post
title: "Getting started with Rails_Admin and Setting Your Admins"

---


<p><a href="http://www.twitter.com/sabrina">Sabrina Majeed</a> and I decided to get together on Labor Day Weekend and put together a Hackathon project from scratch (launch date pending her return from London). While she was busy with the front end, I took the plunge into the world of Ruby on Rails. I learned some very very basic lessons along the way, so I'll share little snippets of these things for those of you looking to jump on the bandwagon as well. </p>

<p>After I set up the framework for our site, I realized that we needed an easy way to manage content from a community. After a few seconds of google searching, I discovered the <a href="https://github.com/sferik/rails_admin">Rails_Admin</a> gem. All I had to do was install a few things and I had an easy to use GUI that could manage all the data on my site.</p>

<div class="lemphasis"><b>Step 1:</b></div>

Add the Rails_Admin gem to your Gemfile 

	gem 'rails_admin'

<br />

<div class="lemphasis"><b>Step 2:</b></div>

Install the gem by running
	
	$bundle install

<br />

<div class="lemphasis"><b>Step 3:</b></div>

Run a generator to install RailsAdmin and Devise. 

	$rails g rails_admin:install

Devise is pretty awesome because it'll set up a whole user system for your app. It takes care of authentication and generates all the login/registration for you. So during the installation, make sure to say yes when you are asked if you want to install Devise. Only good things can come from this.

<div class="lemphasis"><b>Step 4:</b></div>

Finally run:

	$bundle exec rake db:migrate

This will apply all the changes you have made to the schema. 

... And you're all set! 

Start your rails server:

	$rails s

Go to localhost:3000/admin and you'll see your beautiful admin dashboard! You can do all sorts of fun stuff here like taking down posts, removing users, and all the other things a great admin would do! But there's one problem... As of now, anyone can access this admin area of your app if they're smart enough to type in this URL. We should definitely go ahead and specify who has access to this area of your app. 

At this point in my own adventures, I went down the path of using a gem called <a href="https://github.com/ryanb/cancan">CanCan</a> to create this admin role. After consulting Nathan, one of the rails engineers that I work with, he told me that this was actually a far more complicated method of accomplishing my goal. For those of you who do want a more complex role structure in your app, I would recommend that you go with CanCan. However, if you're a n00b like me, you can take the super straightforward approach that I will outline below.

<div class="lemphasis">
	<b>Step 5:</b>
</div>

Rails_admin generated a config file in the initializers folder that lets you manage how the admin feature works. This folder is where all plugins and gems are meant to be configured, so this is definitely the place to go if you want to specify who has access to the admin area. 

<font color="#00786e">app/config/initializers/rails_admin.rb</font>

	config.current_user_method { current_user } # auto-generated
    config.authenticate_with {} # leave it to authorize
    config.authorize_with do
    	is_admin= ADMIN_EMAILS.include?(current_user.email) 
    		if current_user
    			redirect_to main_app.new_user_session_url unless is_admin 
  			end

Some tutorials will tell you to have something in the 'authenticate_with' area, but for now I'm leaving that part out and going straight to 'authorize_with' because we can just handle authentication there. 

Basically I am generating a boolean variable to check if the e-mail address coming through is an admin or not. Then I am checking to see if the person coming through is even a user. If so, I will redirect them to the actual app unless they are an admin. In which case, they will be able to enter the coveted admin dashboard! 

The only piece of the puzzle that we are missing is defining the actual ADMIN_E-MAILS array, so go ahead and define that at the very top of your config file. If you are working with a partner like I am, it'll be an array with 2 emails.

<font color="#00786e">app/config/initializers/rails_admin.rb</font>

	ADMIN_EMAILS= ['youremail@email.com', 'email2@email.com']

Now if you go to localhost:3000/admin, it should prompt you to sign in. If you log in or are logged in already with your admin credentials, you should be good to go.  Otherwise you will just get redirected to the home page. 

...And we're done. Thanks for reading!



