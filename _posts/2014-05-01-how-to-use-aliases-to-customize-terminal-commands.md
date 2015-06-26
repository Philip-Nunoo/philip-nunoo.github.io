---
layout: post
title:  How to use aliases in Linux Terminal.
date:   2014-05-03 8:15:01
categories: Linux, Ubuntu
published: false
---

Most people find it difficult in  using the command line commands, as some commands
are very long and as such make it had to remember and use. With aliases one can always create an alias name for a command.

Aliases are an easy way for you to customize the commands by giving them aliases(nicknames). You can use them to remember hard commands or make short names to long
commands.
</p>

## Setting up Aliases
To setup an alias name, you could directly type the name unto your shell. Like
{% highlight sh %}
alias new_name = "old_command"
{% endhighlight %}

This method is easy when you just need a alias for a single run. But most of the time that alias is lost upon closing the terminal. And one needs to reset that alias again to make use of it.

A much better way to do this is to create a file ".bash_aliases", within your home directory. This file would remain hidden upon its
creation. Pressing "Ctrl+H" would unhide the file for view.

## Aliases Syntax.
You'll need to open the file created with an Editor and add the aliases in them as shown above.

## Some Uses of aliases.
Aliases can generally be used to shorten long commands eg.

{% highlight sh %}
alias agi="sudo apt-get install"
alias agr="sudo apt-get remove"
alias agu="sudo apt-get update"
alias acs="apt-cache search"
{% endhighlight %}

If you are familiar with the shell commands you'll know what the 
commands stated above does.

After setting up the aliases above one could easily execute the commands below which would correspond to their default command.
{% highlight sh %}
agi
agr
agu
acs
{% endhighlight %}

Aliases could be used to also create a path to a document eg.

{% highlight sh %}
alias documents="cd ~/Documents"
alias downloads="cd ~/Downloads"
alias railsFolder="cd ~/Documents/Rails\ \&\ Ruby/"
{% endhighlight %}

This would directly link you to the intended directory name and 
save you the time in typing all the long name within the shell.

Now aliases is a great tool to help you feel comfortable in using the linux terminal. Share any wonderful ways or using aliases if you have any.
