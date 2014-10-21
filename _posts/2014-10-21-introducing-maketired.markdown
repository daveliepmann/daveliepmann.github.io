---
layout: post
title:  "make tired"
date:   2014-10-21 01:19:15
categories: clojurescript cordova release
---
I am releasing **[make tired](/maketired)**, a conditioning workout generator for
iOS. It's an iPhone and iPad app I made that creates short, intense
workouts to make you tired after strength training.

The idea is that you do your regular strength training and then use
the app to whip up a random conditioning workout. It might give you a
fundamental workout, for instance:

{% highlight clojure %}
{:workout "burpees for time"
 :timer-init 300}
{% endhighlight %}

...or the app might randomly generate a circuit from a set of
templates. Here's a subset of those templates:

{% highlight clojure %}
[:push :pull :abs]
[:explosive :whole-body :active-rest]
[:whole-body :upper-body :abs]
[:upper-body :lower-body :whole-body :rest]
{% endhighlight %}

Using one of these methods, the app creates a workout between 5 and 20
minutes long. The workout includes a timer and exercise instructions,
though the user is assumed to have a basic level of knowledge in these
already. (In the future I'd like to add GIF-style exercise demonstrations.)

I built it using ClojureScript and Cordova. Many thanks go to [Leitha Matz](http://www.leithamatz.com/),
[Lauren Papot](http://laurenpapot.com/), and [Jack Rusher](http://jackrusher.com/) for design feedback and test drives.
