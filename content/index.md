---
eleventyNavigation:
  key: Home
  order: 1
numberOfLatestPostsToShow: 3
---

# Hello and welcome!

If you've just set up your new 11ty base blog and would like to find some new themes for it, you've actually come to the right place this time ;)

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
