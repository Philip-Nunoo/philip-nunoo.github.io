---
layout: post
title:  "Starting with Jekyll!"
date:   2014-04-20 10:50:11
categories: jekyll programming
summary: "Jekyll is a static website generator developed in Ruby.
I was excited to know at first that you could actually host your site of Github pages with
Jekyll. And this gives an easier hosting method."
---
[Jekyll][jekyll] is a static website generator developed in [Ruby][ruby].
I was excited to know at first that you could actually host your site of Github pages with
Jekyll. And this gives an easier hosting method.
<p>
Mr. Obama even used [Jekyll][jekyll] during his campaign.
</p>
<p>
Now i'll talk about how to setup Jekyll and some of the challenges I faced
</p>

<div>
<h1>Getting Started</h1>
I started developing with Ruby on Rails so for the requirements of ruby I already
have it installed, with gem also installed.
The setup process is quite easy and the only problem which I faced was 
actually from my end and it was with the proxy. 
<p>
The full process of installing and starting Jekyll shown here:
</p>
</div>
<div>
{% highlight sh %}
~$gem install jekyll
~$jekyll new my-site
~$cd my-site
{% endhighlight %}
</div>
<p>
As I said the only problem which arose initially was me being able to 
get jekyll itself. I usually move around so I often face proxy changes here
and there.
</p>
<p>
So I had to fixed that on my terminal by doing the following before running
gem install jekyll
</p>
<div>
{% highlight sh %}
~$export http_proxy=""
~$export https_proxy=""
{% endhighlight %}
</div>
<p>Ok thats it so I had jekyll ready to use</p>
<p>You can run gem list and find out if you have jekyll in there.</p>
{% highlight sh %}
~$gem list
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll's GitHub repo][jekyll-gh].

[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]:    http://jekyllrb.com
[ruby]:      http://www.ruby-lang.org/en
