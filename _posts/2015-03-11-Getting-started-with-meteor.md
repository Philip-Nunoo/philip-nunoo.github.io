---
layout: post
title: Getting started with meteor
published: true
categories: javascript, meteor, programming
---
<img src="{{ site.baseurl }}/assets/meteorjs.png"/>
For four months now I've been using meteor to developing projects at a pace I've never dreamt. And I think it's a great tool if you wish to get an MVP out there in no time or win a hackathon. 

Metoer, I would say can be a great starter for beginner developers, in that it could be used to build impressive and useful applications in no time. 

Metoer has grown over some couple of years as being a framework that both serves frontend needs and also backend needs. Thereby no need for frameworks such as angular or react.

Once you dig deep down into meteor you'd appreciate a lot of functionalities that meteor brings to the table. And also the simplicity of cooking up either a login screen or an admin page with a help of a package.

## How to get meteor on your system
How do I get and start using meteor? 
Meteor fully support OS X, Windows, and Linux.

On windows, download the official Meteor Installer from here

On OS X or Linux, you can install the official meteor release from the terminal

```shell
curl https://install.meteor.com/ | sh
```

once you've installed meteor you can start creating all of your meteor projects with the meteor command

```shell
meteor create <app_name>
```

__replace <app_name> with the name of your app.

This creates a directory bearing the name given thus the app_name and within it you'd have three basic files that comes with it(a <app_name>.css file, <app_name>.js file, and <app_name>.html file).

There you have it your first meteor application. Guess you didn't expect this but that's what you get when you create a new meteor project. Meteor gives you these basic files to work with. There are a number of boilerplates which basically defines a way you could structure your application by placing code  into files and their respective directories.

You can run your app with the command

```shell
meteor
```

or

```shell
meteor run -p 4000
```

The -p option specifies which port you would wish to use.
You'd get the following screenshot on running

<img src="{{ site.baseurl }}/assets/metoer_post_10.png"/>

In my next post would talk about the meteor structure and how you could use it to in developing your project. I believe these are somethings one should really understand before 
