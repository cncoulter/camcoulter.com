---
SPDX-FileCopyrightText: 2022 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: default
title: "ReadMe"
permalink: /About-This-Site/ReadMe/
---

# ReadMe

This website is a work-in-progress. This will be my personal website/blog.

## Done

* <code>jekyll new camcoulter.com --blank</code>
* Host codebase on GitHub
* Host site with Netlify
* Add 404 page
* Make website [REUSE-compliant](https://reuse.software/)
* Add dark mode
* Add About This Site
	* Accessibility Statement
	* Website Design & Hosting
	* Copyright
* Create system (and collection) for images
* Create image include and set site-wide default image
* Add About
	* Short bio
	* Photo
* Add Blog
	* Add all blog posts
	* Add category index and tag index
	* Add featured images
	* Add [TOC](https://github.com/toshimaru/jekyll-toc) to `_layouts/post.html`
* Add container
* Add Publications
* Smooth scrolling except when prefers reduced motion
* Skip to Main Content link
* Add head/meta
* Add Site Map
* Add favicon
* XML sitemap
* Add fonts

## To-Do Soon

* https://poormansstyleguide.com/
* Style:
	* Responsive typography
	* h1, h2, etc
	* code element
	* header
	* footer

### Filling Out Content & Style

* About This Site
	* Privacy Policy
* About
	* Add rest of content
* Blog
	* Style posts
	* Style blog home
* Projects

* Style header
* Style footer
* Add print stylesheet
	* https://www.matuzo.at/blog/i-totally-forgot-about-print-style-sheets/
* Add responsive typography
* Style templates
* Style Blog pages
* Style code element

### More Advanced Features

* Press button style
* Add web feeds
	* https://validator.w3.org/feed/docs/atom.html#text
	* https://css-tricks.com/working-with-web-feeds-its-more-than-rss/
	* Try to add RSS, Atom, & JSON, lol?
	* Different feed options for: 10 recent posts vs all posts; reading+SFF vs tech+a11y?
* Add search form: https://kevq.uk/how-to-add-search-jekyll
* Add dark/light mode toggle
	* https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model
	* Examples/Inspiration:
		* <https://12daysofweb.dev/2021/preference-queries/>
		* <https://a11y.coffee>
		* <https://oinam.github.io/oinam-jekyll/>
* [prefers-contrast](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-contrast) (high contrast mode)
* Add contact form
* Add focusable heading anchor links
* Add blogrolls
* Add breadcrumbs (WCAG 2.4.8)
	* Reference/inspiration:
		* <https://meiert.com/en/blog/html-common-idioms>
		* <https://www.w3.org/WAI/WCAG21/Techniques/general/G65.html>
		* <https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Breadcrumb_Navigation>
* Add summaries (like [Lainey Feingold's website](https://www.lflegal.com/2021/11/overlay-legal-update/))
* Try to meet additional WCAG AAA success criteria
* Optimize sizes attribute for images
* Expanding/collapsing mobile navbar

### Publishing

* Add [Plausible](https://plausible.io/) analytics
	* UTM parameters?
* site verification
	* google-site-verification
	* bing, too

### Misc Inspiration
* https://ericwbailey.design/
* https://yatil.net/blog
* https://www.tempertemper.net/blog/if-html-and-aria-dont-allow-it-its-probably-a-bad-idea
* https://danabyerly.com/notes/dear-html-element/
* https://kevq.uk/posts/
* https://www.matuzo.at/blog/html-boilerplate/
* https://css-irl.info/dont-forget-the-lang-attribute/
* https://css-irl.info/
* https://css-irl.info/accessible-toggles/
* https://www.smashingmagazine.com/2021/10/respecting-users-motion-preferences/
* https://www.craigabbott.co.uk/blog/defining-a-strategy-for-accessibility

## Documentation/Notes to Self

### Liquid

Read Liquid documentation at: <https://shopify.github.io/liquid/>.

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
