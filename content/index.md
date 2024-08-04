---
eleventyNavigation:
  key: Home
  order: 1
numberOfLatestPostsToShow: 3
---

# Hello and welcome!

If you've just set up your new 11ty base blog and would like to find some new themes for it, you've actually come to the right place this time ;)

## What is this?

We've now seen several people wanting to use 11ty but finding the path complicated, and frustratingly lacking in applicable themes.

Seeing as the [eleventy-base-blog](https://github.com/11ty/eleventy-base-blog) is such a good place to start, it makes sense to have a bunch of themes ready to drop into it.

This website will showcase some themes made with CSS stylesheets for use with the 11ty base blog, and make them easily downloadable.

{% set postsCount = collections.posts | length %}
{% set latestPostsCount = postsCount | min(numberOfLatestPostsToShow) %}
<h2>Latest {{ latestPostsCount }} Post{% if latestPostsCount != 1 %}s{% endif %}</h2>

{% set postslist = collections.posts | head(-1 * numberOfLatestPostsToShow) %}
{% set postslistCounter = postsCount %}
{% include "postslist.njk" %}

{% set morePosts = postsCount - numberOfLatestPostsToShow %}
{% if morePosts > 0 %}
<p>{{ morePosts }} more post{% if morePosts != 1 %}s{% endif %} can be found in <a href="blog.njk">the archive</a>.</p>
{% endif %}

{# List every content page in the project #}
{#
<ul>
	{%- for entry in collections.all %}
	<li><a href="{{ entry.url }}"><code>{{ entry.url }}</code></a></li>
	{%- endfor %}
</ul>
#}
