---
SPDX-FileCopyrightText: 2022 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Website Redesign"
published: true
date: 2019-03-02 00:15
categories:
- web design
tags:
- blogging
- Jekyll
- Bootstrap
- GitHub
description: "Over the last two months, I taught myself the Bootstrap framework for web development, and I used it to redesign my website/blog."
image: code-01
toc: true
---

## Introduction

Over the last two months, I taught myself the [Bootstrap](https://en.wikipedia.org/wiki/Bootstrap_(front-end_framework)) framework for web development, and I used it to redesign my website/blog. This project [was on my to-do list]({{ site.baseurl }}{% post_url 2017-04-27-New-Blog-New-Website %}) since April 2017, and I'm glad that I had the chance to get it done this season. The blog looks much better now.

{% include image.html image="Coulter-oldBlog" %}

## Bootstrap

Bootstrap is a fabulous tool, and I think it should be taught to beginners right alongside HTML and CSS because if you want to do some basic web design-y things (like add a navbar), it's actually quite a bit of work if you're just using HTML and CSS, but with Bootstrap, it's a cinch. And it'll look good. The basics of Bootstrap aren't much more complicated than the basics of HTML, and Bootstrap has another significant advantage: Bootstrap is a tool for developing *responsive* websites, websites that shift their layout depending on whether the reader is accessing the site on a desktop, tablet, or phone.

It also turns out that Bootstrap integrates really well with [Jekyll](https://jekyllrb.com/), the platform that powers my blog, which made this redesign quite a bit of fun.

## What's New

Thanks to Bootstrap, my website/blog is now responsive, so it'll look nice whether you access it on your desktop or your phone.

I added color and photos to the blog, simple design basics that I had neglected before. They do a lot of good, go figure.

I've added support for both [categories]({{ site.baseurl }}/Blog/Categories) and [tags]({{ site.baseurl }}/Blog/Tags).

I also added support for [Twitter cards](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/abouts-cards), so that when I post blog links on Twitter, Twitter adds a nice little box with the post's featured image and an excerpt. Like so:

{% include image.html image="Coulter-TwitterCard" %}

And, of course, in the process of redesigning the website, I also made lots of other small typographical and design edits. All in all, I've very happy with the site now.

## Forking My Website/Blog

[This website/blog]({{ site.baseurl }}/About-This-Site/) is powered by Jekyll and [hosted](https://github.com/cncoulter/cncoulter.github.io) for free on Github thanks to [Github Pages](https://pages.github.com/).

It's a pretty sweet setup because it means: I don't pay hosting fees; the website is super easy to backup; it's easy to host elsewhere if I decide to ditch Github. Also, I was able to set up a custom email and email forwarding for free through Google Domains.

If you're looking to set up your own website/blog, you're welcome to fork my website on Github and use it for yourself. In an [earlier post]({{ site.baseurl }}{% post_url 2017-04-27-New-Blog-New-Website %}) I reflected on the benefits of using Jekyll and Github Pages over a platform like WordPress, so check out that post for more details. It's a little complicated, but if you're tech-savvy, you can probably figure it out okay. Feel free to shoot me an email if you've got any questions.
