---
layout: post
title:      "Simple Nesting "
date:       2020-06-02 12:06:57 +0000
permalink:  simple_nesting
---


I have a project with a User model and an Adventure model. By the end of my project, I'd like for a User not only to see all Adventures but to see Adventures created by certain Users. Let me explain my process in 2 steps. 

**Step one:** set up the association in the models and the routes as such:

Models:

```
class User < ApplicationRecord
  has_many :adventures
end
```

```
class Adventure < ApplicationRecord
  belongs_to :user
end
```

Routes:

```
Rails.application.routes.draw do
  resources :users
  resources :adventures

  resources :users do
    resources :adventures, only: %i[new create index]
  end
```

Why am I nesting again?

It's about the URLs, methods and permissions.

Nesting the adventures resource under users gives me the following paths:

user_adventures_path(user):


```
'/users/:user_id/adventures'    
```

adventures_path:

```
'/adventures'
```

As well as the ability to call '.adventures' on and instance of User to see that user's adventures.

**Step two: Implementation**

Both paths lead to the adventures controller index action. 

However, one has  "/:user_id" passed as a parameter. How can I use that?


```
class AdventuresController < ApplicationController

  def index
    if params[:user_id] && @user = User.find_by_id(params[:user_id])
      @adventures = @user.adventures
			
    else
      @adventures = Adventure.all
    end
  end
```

The first part of index checks to see if an ID is present and in the database. If so, we set the instance variable @adventures to the given User's adventures.

If not, the index action will lead to a view that set the variable to all Adventures. 

Now the easy part is putting the links into html. For simplicity, I placed both paths on my 'home page' as such:

```
  <%= link_to "All Adventures", adventures_path %>

   <h4>By User</h4>
	 
<% User.admins.each do |admin|%>
    <%= link_to admin.email, user_adventures_path(admin) %>
    <br>
    <br>
    <% end %>
```

The first link is pretty straightforward. 

With the second, I created the scope method '.admins' which selects all Users with an  :admin attribute set to 'true', and then displays their specific user_adventures_path.






