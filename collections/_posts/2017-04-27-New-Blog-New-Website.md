---
SPDX-FileCopyrightText: 2022 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "New Blog, New Website"
published: true
date: 2017-04-27 13:15
date_modified: 2022-02-04 13:18
categories:
- thoughts
- web design
tags:
- blogging
- WordPress
- Jekyll
- Github
description:
- For almost a year now, I have been blogging at <https://cameronncoulter.wordpress.com/>, blogging largely about what I've been reading. Now, however, I've migrated my blog to <http://www.cncoulter.com>.
description: "I've migrated from WordPress to Jekyll."
image: code-01
---

For almost a year now, I have been blogging at <https://cameronncoulter.wordpress.com>, blogging largely about what I've been reading. Now, however, I've migrated my blog to <http://www.cncoulter.com>. [Edit: And now, in 2022, I've moved my site over to <https://www.camcoulter.com>.]

So what's up with that, you ask?

I've decided that I want to start submitting poetry for publication, and before I do that, I wanted to set up a website and mailing list. It made sense to migrate the blog over to the new website.

As the [About This Site]({{ site.baseurl }}/About-This-Site/) page will tell you, this website is powered by [Jekyll](https://jekyllrb.com/) with the theme [Jekyll Now](http://www.jekyllnow.com/) and hosted on [Github](https://github.com/cncoulter/cncoulter.github.io) thanks to [Github Pages](https://pages.github.com/). But what all does that mean?

Jekyll is a static site generator. You give it some config files and a bunch of markdown files, and Jekyll generates a static website; that is, a website made up of HTML and CSS files and the like --- no server-side scripting or databases. There are [tons](http://jekyllthemes.org/) of themes you can use to make your Jekyll website look pretty with relatively little work, and it's also fairly straightforward to customize the structure and style of your site. I started with the Jekyll Now theme and then tweaked it for my needs, adding a landing page, a blog archives page, and more.

Once I decided to set up a website and blog, my first thought had been to use Wordpress. Wordpress is simple to use, but also loaded with features. I have happily been using it to blog for the last year, and I also have experience installing Wordpress via the command line. However, I also had to consider hosting costs. If I used a professional Wordpress hosting service (like Wordpress.com or HostGator), I wouldn't have to worry too much about backups (as the service would largely take care of that for me), but professional Wordpress hosting services are more costly than I like. After all, I'm setting up this website for my writing, something which currently isn't making me any money, so I'd rather not spend $100 a year on a website if at all possible.

Of course, I could also host Wordpress myself on a VPS. This would still have a cost, but it'd be cheaper than using a professional Wordpress hosting service. The dilemmas with this option, however, are security and backups. If I run my own server, it's my responsibility to ensure the website is secure. Now, I'm fairly tech-savvy; I believe I can secure a Wordpress server well enough for my needs, but I'd rather offload this responsibility to professionals if possible. Additionally, backups are important, but backups with Wordpress are tricky because Wordpress is complex. You have your website (the `/var/www/` folder), the database which powers your website, and you also have your config settings on your server.

So I researched the question, and I decided to use Jekyll instead. Jekyll doesn't have all the bells and whistles of Wordpress, but it has enough features to meet my needs. Thanks to Github Pages, I can host my Jekyll website for free. However, I'm not tied to Github; I can easily migrate my Jekyll website to a VPS or another hosting service if I wish. Also, backups with Jekyll are beautifully simple. My website is a git repository. If my server crashes, no worry; I've got a copy of the repo on my desktop computer. If my desktop computer crashes, no worry; I can clone the repo from the server.

There's one downside to using Github Pages: if I choose to use a custom domain name (as I have done) (instead of using a URL that looks like cncoulter.github.io), I can't configure my website to use HTTPS, a protocol that encrypts the connection between your web browser and the server. This means that your ISP and sysadmin can see which pages on my website you load. With HTTPS enabled, your ISP and sysmin (and other snoops) can still see that you are connecting to my website, but they can't identify which specific pages you are viewing. This is, as I said, a downside, but it doesn't eclipse the other benefits of Jekyll and Github Pages. I'd like to have HTTPS enabled, but given that no one will be conducting sensitive business on my website, it isn't vital. (That said, if you can figure out a good way to setup HTTPS on Github Pages websites that use a custom domain name, please let me know.)

I also found out a way to have a custom email for free. I got my domain name from Google Domains, set up email forwarding, and then followed [Google's instructions](https://support.google.com/domains/answer/3251241?hl=en) to send mail from my forwarded email address. This way, I can use a custom email address without setting up an email server or paying $5/month for [G Suite](https://support.google.com/domains/answer/6069226?hl=en).

If you're a writer looking to set up your own website, I'd like to point out that you are welcome to fork this website's repository on Github and use my website as a template for your own. Now, admittedly, my website isn't all that pretty, but it is functional and hosted for free. (At some point in the future, I am planning to do a pretty redesign of my site using [Bootstrap](https://getbootstrap.com/).) The website code is licensed under the MIT license, a free and open source license that allows you to modify, distribute, commercially use the software. Feel free to shoot me an email should you have any questions about the process.
