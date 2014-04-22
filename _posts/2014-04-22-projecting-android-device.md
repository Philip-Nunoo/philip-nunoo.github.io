---
layout: post
title:  Projecting android device.
date:   2014-04-22 10:50:11
categories: android programming
---

Your are reading this cause I believe you're also wondering how you could find a 
way to project your android screen. With <a href="[droidatscreen]">droid at screen</a> you can easily
show your device on your desktop(Linux, Mac, Pc... etc.).

It actually works across multiple platforms with the Java Runtime installed, so 
that's one interesting thing about [droid at screen][droidatscreen] .
</p>
<img src="{{ site.baseurl }}/assets/screen1.png"/>
The only downside to [droid at screen][droidatscreen] is its transfer rate(frame rate) from your
device to the on screen display.
You cannot change the rate of transmission on screen. So you actually see the effect
of your events on the phone happening some few seconds delay.

## Download and Installation

You can download droid at screen from [here ][droidatscreendownload], being provided
by [ribomation][droidatscreen] . The current downloadable version as at this post
is [version 1.1][droidatscreendownload]. 

### Installation

To install [droid at screen][droidatscreen] you will need to have Java <abbr title="Java Runtime Environment">JRE</abbr>(or <abbr title="Java Development Kit">JDK</abbr>)
on your development machine. Get the [java installer from Oracle][jdkdownload] and go for 
version 6 or later.

After installing your <abbr title="Java Runtime Environment">JRE</abbr>(or <abbr title="Java Development Kit">JDK</abbr>) make sure you have android <abbr>SDK</abbr>). Droid at Screen uses 
the android SDK, specifically <abbr title="Android Debug Bridget">ADB</abbr>). [Download and install][androidsdk] the Android SDK. 

Go to our SDK Manager and make sure you have Android SDK Platform-tools installed. And you 
good to go in starting your droid at screen.

### Android device

If you haven't already make sure you turn/enable USB debugging on your phone or device.
Open settings choose Developer Option, and finally, ensure USB debugging is selected.

You are to also check to see if your USB drivers for your phone or device is installed.
Please try and get the drivers from your vendors support page.

### Usage

From your terminal locate where you download the droidAtScreen-1.*.*.jar file and run

{% highlight sh %}
~$ java -jar droidAtScreen-1.*.*.jar
2014-04-22 21:00:04,291 DEBUG DroidAtScreenApplication - parseArgs: []
2014-04-22 21:00:04,294 DEBUG DroidAtScreenApplication - initProperties
2014-04-22 21:00:04,324 DEBUG Settings - --- Application Settings ---
2014-04-22 21:00:04,554 DEBUG Settings -   adbExecutable: /home/philip/adt-bundle-linux-x86_64-20131030/sdk/platform-tools/adb
2014-04-22 21:00:04,555 DEBUG Settings -   hideEmulators: false
2014-04-22 21:00:04,556 DEBUG Settings -   imageFormat: PNG
2014-04-22 21:00:04,556 DEBUG DroidAtScreenApplication - initCommands
2014-04-22 21:00:04,587 DEBUG DroidAtScreenApplication - initGUI
2014-04-22 21:00:06,403 DEBUG DroidAtScreenApplication - initAndroid
2014-04-22 21:00:06,521 DEBUG DroidAtScreenApplication - run
2014-04-22 21:00:06,542 DEBUG DroidAtScreenApplication - postStart
2014-04-22 21:00:07,857 INFO  AndroidDeviceManager - ADB changed
2014-04-22 21:00:07,859 INFO  AndroidDeviceManager - Connected to ADB via /127.0.0.1:5037
.
.
.
{% endhighlight %}

replace *.* with the version number downloaded.

… which is shown in the screenshot below:
<img src="{{ site.baseurl }}/assets/droidatscreen.png"/>
on windows you can double click on the .jar file and it 
would start droid at screen for you.

You'll need to specify the location of your <em>adb.exe</em> file
in your android SDK file.

/sdk/platform-tools/adb.exe

Download droidAtScreen:

* [Version 1.1][droidatscreendownload].
* [Version 1.0.2][droidatscreendownload2].
* [Version 1.0.1][droidatscreendownload1].

[droidatscreen]:          http://droid-at-screen.ribomation.com
[droidatscreendownload]:  http://droid-at-screen.ribomation.com/?ddownload=127071
[droidatscreendownload2]: http://droid-at-screen.ribomation.com/?ddownload=557
[droidatscreendownload1]: http://droid-at-screen.ribomation.com/?ddownload=556

[jdkdownload]:            http://www.oracle.com/technetwork/java/javase/downloads/index.html
[androidsdk]:             http://developer.android.com/sdk/index.html
