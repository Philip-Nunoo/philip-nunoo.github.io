---
layout: post
title: Installing And Running Phoenix, Elixir
published: false
categories: elixir, phoenix, programming, ubuntu
---

Today I'd go over the process I used in installing phoenix and running it on mine ubuntu/Linux system

From the phoenix site a link is provided to get the download and installation done onto your system

git clone https://github.com/phoenixframework/phoenix.git && cd phoenix && git checkout v0.6.0 && mix do deps.get, compile

Then after installation you would want to try or create a new phoenix project using the command

mix phoenix.new my_app /path/to/scaffold/my_app

I realized that the 'phoenix.new' command worked while I existed in the phoenix directory that was created through the cloning process on the phoenixframework. And the path I moved it to a path of my chosen. And that was it. This would not take really long while to work around. And I found it very comforting and easier than I'd espected.

With that been done, I head to the directory that was created in view of the last command that was run to run mine phoenix app for the first time.

mix phoenix.start

With phoenix.start I realized an error message being shown here which was understandable. It looked liked some packages or libraries would also have to be installed before we could start phoenix.

Doing this
mix do deps.get, compile

and subsequently running the start again

mix phoenix.start

solved the issue and my phoenix was up and running.


Only that it gave me a blank white screen which got me confused. And so would find out what was wrong and would probably make it known in mine next post. Thank you.

Please feel free to leave a comment below so I know your thoughts about the processes about installing phoenix. And if I failed to point out, you would have to have Elixir installed on your system.