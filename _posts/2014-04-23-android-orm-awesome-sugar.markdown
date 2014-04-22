---
layout: post
title:  "Android Awesome Sugar ORM!"
date:   2014-04-20 10:50:11
categories: android programming
summary: "ORM – Object relational mapping has been around for quite some time now. 
Basically it’s a piece of software (regardless of targeted platform), 
which simplifies the connection between objects (as in OOP) and data in database 
(mostly used is tables based relational database), and it exists in order to help simplify 
bridging the gap between the two in our development process."
---
<p>
<h1>ORM</h1>
ORM – Object relational mapping has been around for quite some time now. 
Basically it’s a piece of software (regardless of targeted platform), 
which simplifies the connection between objects (as in OOP) and data in database 
(mostly used is tables based relational database), and it exists in order to help simplify 
bridging the gap between the two in our development process.
</p>
<p>
There is a whole lot of arguments out there talking about the importance 
of using ORM in android. In my opinion I think it's good and saves time
in writing codes in creating databases and tables within your android application.

</p>
<p>
With my search I found a whole lot of ORMs which I could choose from.
<ul>
<li>GreenDAO</li>
<li>ORMDroid </li>
<li>activeandroid</li>
<li></li>
</ul>
Most sites pointing to the use of ORMlite to be the best of all.
</p>
<p>
ORMlite took some of the coding away but still had some of the same
old things I was doing so I had to either stop it and go with the old method(which 
I mostly used without any trouble) or continue searching.
</p>
<p>And I stumbled upon [sugar][sugar]. I found it amazing and nice since It 
actually tried to mimick what is done in Rails(which I use for some of my
server coding). And this is how I went.
</p>
<p>
<h1>Download Sugar</h1>
You could actually download sugar as a .jar file or a library and
include it in your android project.
</p>

<p>
I choose not to speak for satyan the creator of sugar. But from what I 
see sugar chooses to mimick ORM is played in Rails which makes me very excited.
Cause I'm falling in love with Rails and their migrations.
</p>

<p>
<h1>Configuration</h1>
One nice thing I realized with sugar is their way they handle everything, 
taking away all the coding which needs to be done in setting up or creating
an Sqlite database and its associated table and field. 
<p>
Ok so this is the configuration done within your AndroidManifest.xml
Just include "android:name=com.orm.SugarApp" in your application tag.

And add some few meta-data tag in your application tag to get it started.
</p>
{% highlight xml linenos%}
<application android:label="@string/app_name" android:icon="@drawable/icon"
android:name="com.orm.SugarApp">
.
.
<meta-data android:name="DATABASE" android:value="sugar_example.db" />
<meta-data android:name="VERSION" android:value="2" />
<meta-data android:name="QUERY_LOG" android:value="true" />
<meta-data android:name="DOMAIN_PACKAGE_NAME" android:value="com.example" />
.
.
</application>
{% endhighlight %}
</p>
<p>
<h1><i>meta-data</i> tags</h1>
From sugar orm page these are the definitions of the meta data tags.
<table>
<thead>
<tr><th>Metadata</th><th>Description</th></tr>
</thead>
<tr><td>DATABASE</td><td>Name of the generated sqlite database file</td></tr>
<tr><td>VERSION</td><td>Version of your database schema</td></tr>
<tr><td>QUERY_LOG</td><td>Logs the generated Select queries.</td></tr>
<tr><td>DOMAIN_PACKAGE_NAME</td><td>Specify a package name where your domain/entity classes are present. This helps in smoother table creation</td></tr>
</table>

</p>
<p>
With this you are half way with creating your sqlite database in it's now time to
create the entities which basically represent your Tables.
</p>
<p>
I always like to organize my stuff, so I added a new package naming it models within my default package name
And in my "DOMAIN_PACKAGE_NAME", I refrenced to that package.
</p>
Now to create our entities.
{% highlight java linenos%}


public class Book extends SugarRecord<Book> {
	String title;
	String edition;

	public Book(Context ctx){
		super(ctx);
	}

	public Book(Context ctx, String title, String edition){
		super(ctx);
		this.title = title;
		this.edition = edition;
	}
}


{% endhighlight %}

<p>
As at version 1.2 which existed at the time of this blog you'll have to do.
And you'll have to maintain the empty constructor
</p>
<div>
{% highlight java linenos %}
public class Book extends SugarRecord<Book> {
		String title;
		String edition;

		public Book(){}

		public Book(String title, String edition){
			this.title = title;
			this.edition = edition;
		}
}
{% endhighlight %}
</div>
<p>Awesome, that why I say it's awesome sugar</p>
<p>Just by doing this our Table Book would be created when our application is run. Amazing isn't it.</p>
<p>Better than what I used to do at first</p>
<p>
<h1>Basic Usage - CRUD</h1>
Performing CRUD operations are very simple. Just as calling a method on your class.
By extending SugarRecord<E> you get methods which could do all your CRUD operations.
</p>
<p>
Save Entity:
<div>
{% highlight java linenos %}
Book book = new Book(ctx, "Title", "Description")
{% endhighlight %}
</div>
Load Entity:
<div>
{% highlight java linenos %}
Book book = Book.findById(Book.class, 1);
{% endhighlight %}
</div>
Update Entity:
<div>
{% highlight java linenos %}
Book book = Book.findById(Book.class, 1);
book.title = "new title";
book.edition = "new edition";
book.save();
{% endhighlight %}
</div>
Delete Entity:
<div>
{% highlight java linenos %}
Book book = Book.findById(Book.class, 1);
book.delete();
{% endhighlight %}
</div>
Bulk Operations:
<div>
{% highlight java linenos %}
List<Book> books = Book.listAll(Book.class);
Book.deleteAll(Book.class) // clear everything
{% endhighlight %}
</div>
</p>
<p>That's it now we have all the methods necessary to call to perform operations on
our database. And I realized that I didn't need to write all the SQL query
statements needed to do this.
</p>

Check out the [sugar][sugar] for more info on how to use sugar migrations and 
build queries. Fork sugar on their page on [github][sugar-github].

[sugar-github]: https://github.com/satyan/sugar/
[sugar]:    http://satyan.github.io/sugar/
[ruby]:      http://www.ruby-lang.org/en
