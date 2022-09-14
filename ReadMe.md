---
SPDX-FileCopyrightText: 2022 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: default
title: "ReadMe"
permalink: /About-This-Site/ReadMe/
---

# ReadMe

This is my personal website/blog.

* I use the static site generator [Jekyll](https://jekyllrb.com/) to knit this site together. I have written pretty much all the code myself, consciously avoided Jekyll themes and frameworks such as Bootstrap.
* [This site's codebase](https://github.com/cncoulter/camcoulter.com) is hosted on GitHub.
* This website's codebase is [REUSE-compliant](https://reuse.software/). That means each file should clearly indicate the copyright holder and license.
* This site is hosted with [Netlify](https://www.netlify.com/).

To learn more about this website, view [About This Site]({{ site.baseurl }}/About-This-Site/).

## Features to Add

* Optimize sizes attribute for images on homepage
* Add "press" button style
* Add site search
* Add contact form
* Add web feeds in alternate formats/standards
	* Add RSS feed
	* Add JSON feed
	* Reference:
		* <https://css-tricks.com/working-with-web-feeds-its-more-than-rss/>
* Add dark/light mode toggle
	* Reference/inspiration:
		* <https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model>
		* <https://yatil.net/blog/welcome-to-the-dark-side>
		* <https://12daysofweb.dev/2021/preference-queries/>
		* <https://a11y.coffee>
		* <https://oinam.github.io/oinam-jekyll/>

## Inspiration
* <https://yatil.net>
* <https://www.tempertemper.net>
* <https://kevq.uk>
* <https://www.craigabbott.co.uk>
* <https://danabyerly.com>
* <https://css-irl.info>

## Documentation/Notes to Self

### Liquid

Read Liquid documentation at: <https://shopify.github.io/liquid/>.

### Feeds

* Validate your Atom feed here: <https://validator.w3.org/feed/>
* Helpful reference for Atom feeds: <https://validator.w3.org/feed/docs/atom.html>

### Images

Save images to `/assets/images/`. Give images a human-readable name like `desk-keyboard-notebook.jpg`.

Aim for three different file sizes of each image. For example: `desk-keyboard-notebook-600.jpg`, `desk-keyboard-notebook-1200.jpg`, and `desk-keyboard-notebook-2400.jpg`. Remember to create a `.license` file for each image.

#### Image Collection

For each unique image, create a file in `/collections/_images/` for that file. Structure the file as follows:

	{% raw  %}
	---
	SPDX-FileCopyrightText: 2021 Cam Coulter <git@camcoulter.com>
	SPDX-License-Identifier: CC0-1.0
	title: desk-keyboard-notebook
	alt: "A keyboard, a notebook, headphones, and a cup of coffee rest upon a wooden light desk."
	source: "/assets/images/desk-keyboard-notebook-600.jpg"
	srcset: "/assets/images/desk-keyboard-notebook-1200.jpg 1200w, /assets/images/desk-keyboard-notebook-2400.jpg 2400w"
	width: 600
	height: 397
	link: https://unsplash.com/photos/GnvurwJsKaY
	---

	Photo by <a href="https://unsplash.com/@goumbik?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Lukas Blazek</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
	{% endraw %}

The body of the file should be a caption. This file is used with the `/_includes/image.html` file to easily and quickly create the HTML for the image anytime it is needed.

#### Image Include

`/_includes/image.html` makes it easy to add an image. Use the include like so:

	{% raw  %}
	{% include image.html image="desk-keyboard-notebook" %}
	{% endraw %}

You can also use the include to reference a page's featured image like so:

	{% raw  %}
	{% include image.html image=page.image %}
	{% endraw %}

The resulting code will be a figure element, and it will pull the `src`, `srcset`, `alt`, `width`, and `height` values from the corresponding file in `/collections/_images/`. It will also display the caption (if any) stored in that file.

You can also add a class to the figure element like so:

	{% raw  %}
	{% include image.html image="cam-coulter" figClass="About__Headshot" %}
	{% endraw %}

Good alt text is contextual. If a image is used in different contexts, you may want to use different alt text. You can do that with this include like so:

	{% raw  %}
	{% include image.html image="desk-keyboard-notebook" alt="this is different alt text" %}
	{% endraw %}

What if you want to use different alt text for a post's featured image? Include `image_alt` in the frontmatter like so:

	{% raw  %}
	image: desk-keyboard-notebook
	image_alt: "This is alternative alt text."
	{% endraw %}

### Image Metadata

In practice, add a featured image to every post.

However, code this website in such a way that featured images are not technically required:

* If a post lacks a featured image, the post should display the site's default image as the post's featured image.
* If a post lacks a featured image, use the site's default image on the homepage under "Recent Posts".
* If a post lacks a featured image, set the site's default image as the featured image for head metadata purposes.

The same goes for alt text. In practice, be sure to include alt text for every image in the images collection. In practice, code the site such that alt text is only included if it exists.
