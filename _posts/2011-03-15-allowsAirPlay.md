---
layout: post
date: 2011-03-11 12:26:00 
title: setAllowsAirPlay quicktip
---

Here's a quickie. iOS 4.3 opened up AirPlay for 3rd party devices. However, it's unlikely that you'll want to limit your apps to running only on 4.3. To allow your app to run on older version of iOS, you just need to do something like:

{% highlight objc %}
SEL allowsAirplaySelector = @selector(setAllowsAirPlay:);
if([self.moviePlayer respondsToSelector:allowsAirplaySelector]) {
    [self.moviePlayer performSelector:allowsAirplaySelector 
        withObject:[NSNumber numberWithBool:YES]];
}
{% endhighlight %}

That will set the new allowsAirPlay property to YES, without breaking compatibility with older OS versions.