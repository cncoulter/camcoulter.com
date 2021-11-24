---
SPDX-FileCopyrightText: 2021 Cam Coulter <git@camcoulter.com>
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
	* Add category index and tag index
	* Add featured images
	* Add [TOC](https://github.com/toshimaru/jekyll-toc) to `_layouts/post.html`
* Add container

## To-Do

### Filling Out Content & Style

* Add favicon
* Add head/meta
* About This Site
	* Privacy Policy
	* Analytics
	* Features & Non-Features
* About
	* Add rest of content
* Blog
	* Add pagination
	* Add archive
	* Add all posts
	* Style posts
	* Style blog home
* Publications
* Projects
* Style header
* Style footer
* Add print stylesheet
* Add responsive typography
* Style templates
* Style Blog pages
* Style code element

### More Advanced Features

* Add RSS feed
* Add contact form
* Add search form
* Add dark/light mode toggle
	* Examples/Inspiration:
		* <https://a11y.coffee>
		* <https://oinam.github.io/oinam-jekyll/>
* Add focusable heading anchor links
* Add transition/transform to focus styles?
	* Exempt prefers-reduced-motion
* Add multiple RSS feeds
	* One for SFF + books
	* One for A11y + FS
* Add blogrolls
* Add breadcrumbs
* Add summaries (like [Lainey Feingold's website](https://www.lflegal.com/2021/11/overlay-legal-update/))
* Try to meet additional WCAG AAA success criteria

### Publishing

* Add [Plausible](https://plausible.io/) analytics
	* UTM parameters?

### Misc Inspiration
* https://ericwbailey.design/

## Documentation/Notes to Self

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
