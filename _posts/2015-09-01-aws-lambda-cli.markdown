---
layout: post
title:  "AWS Lambda CLI for Clojure"
date:   2015-09-01
categories: clojure aws cli aws-lambda
---
In case you're also playing with [Tim Wagner and Bryan Moffatt's AWS
Lambda walkthrough for Clojure](https://aws.amazon.com/blogs/compute/clojure/),
and in case you have also found Amazon's documentation expanding upon the line,

>You can invoke and test from the command line

less than immediately clear, here is the command line snippet that
I used to invoke my newly-created function:

{% highlight cli %}
aws lambda invoke \
    --function-name clj-hello \
    --payload \"Dave\" \
    output
{% endhighlight %}

The response from your function goes in the file "output", in whatever
location on the filesystem you invoke it from.

Of course the above is equivalent to

{% highlight cli %}
aws lambda invoke --function-name clj-hello --payload \"Dave\" output
{% endhighlight %}
