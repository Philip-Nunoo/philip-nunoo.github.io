---
layout: post
title: Building a one-to-one Relationship on Rails
published: true
categories: ruby, ruby-on-rails, programming
---

Most at times we would want to have a database tables which has  

In relational databases, a one-to-many relationship occurs when a parent record in one table can potentially reference several child records in another table. In a one-to-many relationship, the parent is not required to have child records; therefore, the one-to-many relationship allows zero child records, a single child record or multiple child records. The important thing is that the child cannot have more than one parent record.


In rails one can possibly achieved that through the has_many association. http://guides.rubyonrails.org/association_basics.html

In an association of users having a user and messages he can create.

The User model could be declared like this:

{% highlight ruby %}
class User < ActiveRecord::Base
	has_many :messages
end
{% endhighlight %}

The corresponding migration for both the User and Message would be:

{% highlight ruby %}
class CreateUsers < ActiveRecord::Migration
  def change
    create_table :users do |t|
      t.string :name
      t.timestamps
    end
 
    create_table :messages do |t|
      t.belongs_to :users
      t.datetime :order_date
      t.timestamps
    end
  end
end
{% endhighlight %}