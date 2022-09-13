---
SPDX-FileCopyrightText: 2022 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Website Redesign"
published: true
date: 2022-09-12 17:40
categories:
- accessibility
- web design
tags:
- a11y design
- blogging
- Jekyll
description: "After several months of work, I have finally completed an extensive redesign of my website/blog."
image: code-02
toc: true
---

## Why?

A year ago, [I participated in Knowbility's Accessibility Internet Rally]({{ site.baseurl }}{% post_url 2021-11-11-A11y-Adventures %}/#accessibility-internet-rally) (AIR), a friendly competition in which teams of web designers and developers first learn about web accessibility and then create accessible websites for small nonprofits. For the competition, my team created an accessible [WordPress](https://wordpress.org/) site for our nonprofit partner. I think WordPress is a great tool for small organizations and independent creators who only need a simple website and/or blog. It isn't too challenging to create accessible sites with WordPress, WordPress is a robust platform with many customization and support options, and I think WordPress is usable and understandable for people who are tech-fluent but who may not know anything about HTML or CSS. WordPress was definitely the right choice for AIR.

However, by the end of the competition, I was burned out with WordPress for the time being. AIR was my first experience using WordPress as a designer/developer. It wasn't a bad experience, and I don't think WordPress is a bad option for designers or developers. However, it was too complicated for my liking. My strengths are vanilla HTML and CSS, and it can be challenging to perfectly control the HTML and CSS output of a WordPress site. Throughout AIR, I was itching to use Jekyll rather than WordPress. [Jekyll](https://jekyllrb.com/) is a different tool for creating websites. It's what I use to knit together this site. As a static site generator, I find Jekyll gives me a lot more control over the HTML and CSS output of a website. Over the past two and a half years, I have learned a lot more about HTML, CSS, and web accessibility, and my standards for good, clean, accessible code have developed, and I wanted that additional control that Jekyll could provide.

So what did I do after finishing the AIR program? Naturally, I started a website design project using Jekyll. Specifically, I started to redesign my personal website/blog. I wasn't proud of my existing website's codebase, and I wanted to rebuild it from the ground up.

## A trip down memory lane

My personal website/blog has gone through several iterations over the years.

This blog started in 2016 strictly as a book blog. I've never really posted *reviews* on this blog so much as I shared my thoughts about what I was reading. I read a lot, I have lots of thoughts about what I read, and I like to write, so I started chronicling my book thoughts on a simple WordPress blog, often sharing links to particular posts with my book-loving friends.

In 2017, [I migrated from WordPress to Jekyll]({{ site.baseurl }}{% post_url 2017-04-27-New-Blog-New-Website %}). At that time, I was starting to submit poetry for publication, and I wanted to have a more formal presence online, with my own domain. I decided to use Jekyll because I could host it for free with [GitHub Pages](https://pages.github.com/), because I'm a computer nerd who likes creating websites, and because, as a static site generator, it was generally faster and more secure than WordPress. This was my first experience using Jekyll, so I used [Jekyll Now](https://www.jekyllnow.com/) as my training wheels to help me structure the site. It wasn't a pretty site, but it was clean, functional, and free for me to host. It was around this point that I switched over from publishing blog posts about individual books to publishing "[recent reading]({{ site.baseurl}}/Blog/Tags/#recent+reading)" or "[year in review]({{ site.baseurl }}/Blog/Tags/#year+in+review)" roundups.

{% include image.html image="Coulter-oldBlog" %}

In 2019, I taught myself the Bootstrap framework, and [I used Bootstrap to redesign my Jekyll site]({{ site.baseurl }}{% post_url 2019-03-02-Website-Redesign %}). It was still a simple site overall, but it looked a little more modern and it was no longer so starkly bland. At this point, I started adding a featured image to accompany each post.

In 2020, I started learning about and falling in love with web accessibility. I started [blogging about accessibility]({{ site.baseurl }}/Blog/Categories/#accessibility) on this site, and I conducted a simple [accessibility audit and remediation project]({{ site.baseurl }}{% post_url 2020-11-30-A11y-Updates %}) to improve this site.

{% include image.html image="Coulter-blog-02" %}

In the summer of 2021, I used this blog to study for my Certified Professional in Accessibility Core Competencies (CPACC) credential, writing a "[100 Days of A11y]({{ site.baseurl}}/Blog/Tags/#100+Days+of+A11y)" blog series. In the fall of 2021, I participated in AIR. Then, after AIR, I started this redesign project.

## So what's new?

I am still using Jekyll to knit this site together. I like Jekyll.

However, I am no longer using Bootstrap (or any other framework) to style or design the site, and I am no longer using Jekyll Now or even any Jekyll themes. Instead, I have written pretty much all the code myself, using vanilla HTML and CSS.

{% include image.html image="Coulter-blog-03" %}

This site now supports both light and dark modes. (It automatically adjusts according to your browser preference.)

This site now has a human-readable site map as well as an XML site map, and the blog has a category index, a tag index, and an Atom feed. I've added a table of contents to blog posts that have multiple sections.

This site now has specially designed print styles, so if you choose to print any page, the printout should render nicely. Decorative images will not print, and URLs will be printed in parenthesis next to external links.

This site is now much more accessible. I believe it conforms to the Web Content Accessibility Guidelines (WCAG) 2.1 level AA. Further, I've run most of these pages (and the Atom feed) through the [W3C's markup validator](https://validator.w3.org/), and I have fixed the errors and warnings the validator revealed. This site serves valid code.

This website is now [REUSE-compliant](https://reuse.software/), which means that the copyright holder and license are explicitly indicated for each file in the codebase.

On the [About This Site]({{ site.baseurl }}/About-This-Site/) page, I have added a privacy policy and greatly expanded and improved the accessibility statement and copyright statement.

Also, I switched over to hosting with [Netlify](https://www.netlify.com/) rather than with GitHub Pages.

## How does it feel?

I'm happy with how it turned out, proud of my work, and relieved to be done. I've probably spent about ten months working on this website redesign. That is a good chunk of time. Partially, it took that long because this has been an involved, detailed project. I essentially built this site from the ground up, from scratch. It was a lot of work, and there was a lot I needed to research or learn. Also, this project took ten months because it was only a side project of mine. I didn't work on it every day, or even necessarily every week. There were a few nights or weekends when I could spend a few hours working on this, but most often, I worked on this in 30 minute chunks during my lunch break.

I've learned there's a lot that goes into a website. You may know HTML and CSS, and even WordPress or Jekyll, but do you know about Open Graph Protocol, favicons, typography, RSS/Atom feeds, images, copyright, and accessibility? It gets complicated, and there is *a lot* to consider. It has been a challenge to handle all of this, but it's been a fun challenge, and it's been a good learning experience. Now I know a lot more about not just HTML and CSS but the web as a whole.

I still have a number of improvements and additions to this site that I'd like to make, but these are ancillary changes, garnishes, not essential to the site as a whole, and I'm eager to call it a wrap and move on to other projects, so this is me saying, "It's done! The website redesign is complete!" I'll return here and make those changes when I feel motivated to do so in the future.

Oh, one last thing: I've added a "reply via email" button at the bottom of posts. I don't think comments are appropriate for this blog, but that doesn't mean I want to just write into the void. Please shoot me an email and share your thoughts on what I've written.

What do you think about the new website design? What do you like (or not like)? Do you have any questions for me about this project? Have you spotted any accessibility or usability issues that I've overlooked?
