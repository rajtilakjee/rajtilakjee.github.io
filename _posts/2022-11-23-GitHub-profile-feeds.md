---
layout: post
title:  "How to get your GitHub RSS Feed"
categories: github
---

Here are the links to the RSS feeds of any GitHub repositories, commits, activities etc. It is available for every profile, you simply need to replace the username, repo name, and so on.'\n\n\n'

{% highlight html %}

/* Repo releases */
https://github.com/:owner/:repo/releases.atom

/* Repo commits */
https://github.com/:owner/:repo/commits.atom

/* Private feed (You can find Subscribe to your */
/* news feed in dashboard page after login) */
https://github.com/:user.private.atom?token=:secret

/* Repo tags */
https://github.com/:user/:repo/tags.atom

/* User activity */
https://github.com/:user.atom

{% endhighlight %}

For example, here's the link to the feed of my GitHub activities:

{% highlight html %}
https://github.com/rajtilakjee.atom
{% endhighlight %}

Finally, here's the link to the RSS feed of my blog:

{% highlight html %}
https://rajtilakjee.github.io/feed.xml
{% endhighlight %}
