---
layout: post
title:  "make tired"
date:   2014-10-21 01:19:15
categories: clojurescript cordova release
---
I am releasing **[make tired](/maketired)**, a conditioning workout generator for
iOS. It's an iPhone and iPad app I made that creates short, intense
workouts to make you tired after strength training.

![make tired app screenshot](/maketired/mockups/maketired-iPhone5-equipment_iphone_black_portrait.png)

The idea is that you do your regular strength training and then use
the app to whip up a random conditioning workout. I built it to
scratch an itch, namely, lifting weights renders me temporarily too
stupid to think up my own circuit workout combinations.

So I fired up a Clojure REPL and coded up a list of workouts I
consider fundamental, like:

{% highlight clojure %}
{:workout "burpees for time"
 :timer-init 300
 ;; NB: this example has been greatly simplified
 :instructions "5 minutes"}
{:workout "400-meter sprints"
 :timer-init 0
 :instructions "Three sprints"
 :equipment [:place-to-run]}
{% endhighlight %}

I also created a set of templates into which the app could insert
exercises to generate circuit workouts. The randomness in this process
promises both movement variety and workout novelty.

{% highlight clojure %}
(def templates
    [[:push :pull :abs]
     [:explosive :whole-body :active-rest]
     [:whole-body :upper-body :abs]
     [:upper-body :lower-body :whole-body :rest]])
{% endhighlight %}

Of course, there's a long list of exercises stored as Clojure maps,
each with a set denoting the types of exercises it qualifies as (push,
pull, explosive, *et cetera*).

After the basic workout generation was complete, I used Cordova to
make the ClojureScript-and-HTML UI palatable for XCode.

To see more, check out the [app page](/maketired) and download on the
Apple App Store.

Many thanks go to [Leitha Matz](http://www.leithamatz.com/),
[Lauren Papot](http://laurenpapot.com/), and [Jack Rusher](http://jackrusher.com/) for design feedback and test drives.
