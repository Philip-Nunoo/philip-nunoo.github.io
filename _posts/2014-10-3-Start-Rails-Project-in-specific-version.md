---
layout: post
title: Starting Rails Project in Specific Version
published: false
categories: ruby, ruby-on-rails, programming
---

Sometimes you need to install and create app with specific rails version. To do so you'd have to install that version of rails


To install specific rails version run:

{% highlight ruby %}
gem install rails -v 4.1.1
{% endhighlight %}

When you're done you can install your new rails application through

{% highlight ruby %}
rails _4.1.1_ new app_name
{% endhighlight %}