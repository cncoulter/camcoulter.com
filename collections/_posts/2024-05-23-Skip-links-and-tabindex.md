---
SPDX-FileCopyrightText: 2024 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Same-Page Links and Tabindex"
published: true
date: 2024-05-23 09:00
categories:
- accessibility
- web design
tags:
- HTML
- Jekyll
- a11y
- a11y design
description: "Here's a few things I've learned and a couple changes I've made to this site."
image: code-01
toc: true
---

## Same-Page Links That Work for Everyone
{: tabindex="-1"}

In HTML, it is fairly easy to create same-page links: use the number symbol in a link's href attribute to reference the ID of another element on the page. For example:

```
<a href="#same-page-link-target">Jump to kittens!</a>  
<h2 id="same-page-link-target">Kittens!</a>
```

For a lot of users, that alone is sufficient. But it recently came to my attention that just doing the above won't work equally for all users. Due to various bugs, if you follow the above pattern, focus may not properly shift to the same-page link target for VoiceOver users and keyboard-only users on iOS and for TalkBack users on Android.<sup><a href="#ftn-1" id="ftn-ref-1"><span class="visually-hidden">Footnote </span>1</a></sup> In order to ensure that same-page links work for all users, you'll need to add <code>tabindex="-1"</code> to link targets.

Same-page links can be particularly important for people with disabilities and for people who use assistive technology, so it is important to make sure our same-page links work for everyone. One particularly important same-page link is the "Skip to main content" link that most all pages should have. This should be the first link to receive focus on each page, and it should allow users to skip past the navigation menu and to the main body content. Without a "Skip to main content" link, keyboard users will have to press the <kbd>Tab</kbd> key repeatedly on each page to reach the main content. This can be a frustrating waste time, particularly for people with mobility or dexterity challenges. Another common type of same-page link is a table of contents link that allows users to jump to a particular heading on a page. As you may have noticed, I use these frequently on this site. Footnotes may also use same-page links.

## Site Improvements
{: tabindex="-1"}

On this site, I recently added <code>tabindex="-1"</code> to the "Skip to Main Content" link targets. I've tested the "Skip to Main Content" links on Windows, Fedora, iOS, and Android using my keyboard alone and using screen readers, and I can confirm that my "Skip to Main Content" links are working well for all users. Hurrah!

But what about table of contents links? This was more complicated because this site has many of them and because, for most pages, [Jekyll](https://jekyllrb.com/) uses [Kramdown](https://kramdown.gettalong.org/index.html) to convert a Markdown source file into HTML. Kramdown does not add <code>tabindex="-1"</code> to all generated headings by default, and as far as I can tell, there isn't a way to configure Kramdown to categorically add <code>tabindex="-1"</code> to all headings. (If you know how I can ensure Jekyll/Kramdown adds <code>tabindex="-1"</code> to headings categorically when converting Markdown pages into HTML pages, please let me know!)

However, Kramdown does allow you to add <code>{: tabindex="-1"}</code> directly beneath headings in Markdown, and this will ensure that the generated HTML includes <code>tabindex="-1"</code>. This is helpful, but it does need to be done individually for every same-page link target. Since most of my blog posts have a table of contents with same-page links, that meant I needed to go through and update the vast majority of pages on this site! Which I, in fact, did! I believe all same-page links on this site should now work well for all users.

## Choosing Appropriate Same-Page Link Targets
{: tabindex="-1"}

There's two other relevant things I've learned lately and one other change I've made with same-page links.

As background, the [tabindex attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) has several possible values:

* <code>tabindex="0"</code> allows an element to receive keyboard focus. If you are creating custom controls, you may need to add <code>tabindex="0"</code> to ensure those controls receive keyboard focus.
* A positive tabindex value, such as <code>tabindex="5"</code>, not only ensures that element will receive keyboard focus, but it determines the order in which it will receive keyboard focus. For example, an element with <code>tabindex="5"</code> might be the fifth element to receive keyboard focus on the page, even if it's the very first element on the page, and an element with <code>tabindex="1"</code> might be the first element to receive keyboard focus, even if it's the last element on the page. I can't think of a good reason to ever use a positive tabindex value.
* <code>tabindex="-1"</code> allows an element to programmatically receive keyboard focus. That means, if you are pressing the <kbd>Tab</kbd> key to navigate a page, the element won't receive keyboard focus, but if you for example open a dialog, the site could use JavaScript to shift focus to the dialog's heading. And as we've seen, <code>tabindex="-1"</code> may be necessary to ensure that same-page links work equally for all users.

Here's what I've learned: <code>tabindex="-1"</code> does something else that you may not know. If you add <code>tabindex="-1"</code> to the <code><main></code> element (or a container <code><div></code> as well), then anytime you click somewhere in the <code><main></code> element, keyboard focus will jump to the top of the <code><main></code> element. Personally, as someone who often switches between mouse and keyboard, I find this really annoying. I'll often click just before a control and then press the <kbd>Tab</kbd> key to shift focus to it, but if <code>tabindex="-1"</code> is applied to the <code><main></code> element, that will instead result in my keyboard focus jumping to the top of the main body content, far away from the control I was hoping to interact with.

Here's an example. Here's two paragraphs that each include two links. The first paragraph is in a <code><div></code> element with <code>tabindex="-1"</code> and the second is not. Notice that in the first paragraph, if you click on <cite>The Genesis of Misery</cite> and then press <kbd>Tab</kbd>, Neon Yang receives focus. However, in the second paragraph, if you click on <cite>The Genesis of Misery</cite> and then press <kbd>Tab</kbd>, <cite>The Black Tides of Heaven</cite> receives focus.

<div class="raised" tabindex="-1">
<p><a href="https://neonyang.com/">Neon Yang</a> is an author who has written several books including <cite>The Genesis of Misery</cite> and <a href="https://torpublishinggroup.com/the-black-tides-of-heaven/"><cite>The Black Tides of Heaven</cite></a>.</p>
</div>

<div class="raised">
<p><a href="https://neonyang.com/">Neon Yang</a> is an author who has written several books including <cite>The Genesis of Misery</cite> and <a href="https://torpublishinggroup.com/the-black-tides-of-heaven/"><cite>The Black Tides of Heaven</cite></a>.</p>
</div>

Therefore: do not apply <code>tabindex="-1"</code> to the <code><main></code> element or to container elements. Instead, only apply <code>tabindex="-1"</code> particular controls or headings that you want to shift focus to, and ensure same-page links target specific controls or headings rather than regions.

Here's another thing I've noticed: if you have a same-page link that targets a region (like your <code><main></code> element or a container <code><div></code>), then when a screen reader user follows that link, the screen reader may announce everything in the region. This can result in an exceedingly long announcement, including multiple paragraphs of text, and personally I find it cognitively overwhelming. However, if a same-page link targets just a particular heading, then screen readers will announce just that heading when users follow the link. I think this is a cleaner and less overwhelming experience: you activate a "Skip to Main Content" link, and your screen reader announces the primary page heading and then shuts up and waits for you to move ahead at your own pace.

This is also a change I've made to this site. Previously, my "Skip to Main Content" links targeted the <code><main></code> element, but now I've updated it so that my "Skip to Main Content" links target the primary page heading and <code>tabindex="-1"</code> is applied to just the heading, not to the entire <code><main></code> element.

***

How are my same-page links working for you? Notice any issues with them? Do you know any other interesting facts or intricacies about same-page links?

## Footnotes
{: tabindex="-1"}

<ol>
    <li id="ftn-1" tabindex="-1"><p>At least some of these bugs have been known about for a while now and may even have been patched. It's not entirely clear to me whether these bugs affect all VoiceOver users and keyboard-only users on iOS and all TalkBack users on Android, but that said, these bugs were occurring on my test devices, so I figured that's reason enough to do what I can to ensure my same-page links work for everyone. <a href="#ftn-ref-1" aria-label="Return to text, Footnote 1">&#8617;</a></p></li>
</ol>
