---
layout: photos
title: "Posting Pictures to your Jekyll Blog- Easy Cheesey!!!"
description: "Examples and code for displaying images in posts."
tags: [tutorials, pictures, photos, photo gallery]
comments: true
---



Below are several examples of how you can combine photos with you with Jekyll blog posts.  It's really quite easy and once you get the process down it will become second nature.  

If you want to display a single image with a post you simply enclose the image information inside of a pair of `figure` tags. If you want to include a link to the picture and a caption you should include a `href=` and `figcaption` tags.  

## Figures (for images or video)

### One Up

<figure>
	<a href="{{site.baseurl}}/images/ghostrock.jpg"><img src="{{site.baseurl}}/images/ghostrock.jpg></a>
	<figcaption><a>A 1,000 miles from nowhere.  Ghostrock, Utah</a></figcaption>
</figure>

### Two Up

Apply the `half` class like so to display two images side by side that share the same caption.

```html
<figure class="half">
	<img src="{{site.baseurl}}/images/ghostrock.jpg" alt="">
	<img src="{{site.baseurl}}/images/ghostrock.jpg" alt="">
	<figcaption>Caption describing these two images.</figcaption>
</figure>
```

And you'll get something that looks like this:

<figure class="half">
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<<img src="{{ site.baseurl }}/images/ghostrock.jpg">
	<img src="{{ site.baseurl }}/images/ghostrock.jpg">
	<figcaption>Two images.</figcaption>
</figure>

### Three Up

Apply the `third` class like so to display three images side by side that share the same caption.

```html
<figure class="third">
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<figcaption>Caption describing these three images.</figcaption>
</figure>
```

And you'll get something that looks like this:

<figure class="third">
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<a href="http://placehold.it/1200x600.jpg"><img src="{{ site.baseurl }}/images/ghostrock.jpg" alt=""></a>
	<figcaption>Three images.</figcaption>
</figure>

{% if page.comments %}
<div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
/*
var disqus_config = function () {
this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = '//jajb.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}
