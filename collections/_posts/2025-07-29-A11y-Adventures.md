---
SPDX-FileCopyrightText: 2025 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Accessibility Adventures: July 2025"
published: true
date: 2025-07-29 17:59
categories:
- accessibility
tags:
- a11y
- HTML
- CSS
- ARIA
- documentation
description: "Here’s what I’ve come across lately in the world of accessibility: the remediation gap, focus priming, customization, and various cool new things."
image: refreshable-braille
toc: true
---

## Up and coming!
{: tabindex="-1"}

There’s a lot of new web things out there these days and more incoming. Here’s a roundup of some of those new things that have made it onto my radar. This section is a blend of digital accessibility plus general web design stuff --- the line between those is fuzzy.

### Let’s start with HTML
{: tabindex="-1"}

Here is a delightful roundup of new things in HTML from Chris Coyier: “[Relatively New Things You Should Know about HTML Heading Into 2025](https://frontendmasters.com/blog/bone-up-html-2025/).” I’m happy to see the <code>&lt;search&gt;<code> element, and I’m particularly excited about styleable <code>&lt;select&gt;<code> elements.

### We have `:has`!
{: tabindex="-1"}

The [CSS `:has` pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/:has) is really quite remarkable. If you’re a nerd like me, this pseudo-class is a fun toy for your mind. Here are some pages about it that I like:

* "[The CSS :has Selector (and 4+ Examples)](https://css-tricks.com/the-css-has-selector/)" by Robin Rendle on CSS Tricks
* "[Level Up Your CSS Skills With The :has() Selector](https://www.smashingmagazine.com/2023/01/level-up-css-skills-has-selector/)" by Stephanie Eckles in Smashing Magazine
* "[The Undeniable Utility Of CSS :has](https://www.joshwcomeau.com/css/has/)" by Josh
Comeau
* "[The :has() pseudo-selector](https://html-css-tip-of-the-week.netlify.app/tip/has/)" by Kevin Powell

### CSS-only Carousels
{: tabindex="-1"}

Apparently CSS-only carousels are a thing now. For more, see “[Carousels with CSS](https://developer.chrome.com/blog/carousels-with-css)” by Adam Argyle on the Chrome Developer blog. Kevin Powell’s video “[Learning how CSS-only carousels are going to work](https://www.youtube.com/watch?v=g03Yldh9Nkw)” may also be a helpful introduction.

I dislike carousels, and I see accessibility gaps with the current state of CSS-only carousels. I wouldn’t recommend CSS-only carousels.

That said, I do think it’s important for web accessibility professionals to know this is a thing, and I intend to keep an eye on it. I can imagine this tripping up a novice accessibility consultant who doesn’t know these are a thing.

How do CSS-only carousels work at a high level? In the Chrome Developer blog post, Adam Argyle writes: “A carousel is a scroll area with up to two added UI affordances—buttons and markers.” I think that sums it up at a high level. CSS carousels are a scroll area, one where buttons are actually added via CSS. (Yep, you read that right.)

“[Are 'CSS Carousels' accessible?](https://www.sarasoueidan.com/blog/css-carousels-accessibility/)” by Sara Soueidan is a really thoughtful exploration of CSS-only carousels and accessibility. If you’re interested in this (or if you’re unfortunate enough to be dealing with this), I’d recommend giving it a read.

### `command` and `commandfor`
{: tabindex="-1"}

Here’s something else from the Chrome Developer blog, something I’m more excited about: “[Introducing command and commandfor](https://developer.chrome.com/blog/command-and-commandfor).” The `command` and `commandfor` attributes for `&lt;button&gt;` elements can give you an “HTML way” to make buttons open and close modal dialogs and more. Personally, I’ve always found it a little weird just how much interactivity is buried in JavaScript and not necessarily visible from HTML. These attributes can make that connection a little more clear, and that’s something I will welcome. Read more about these attributes on [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/button), in [HTML standard](https://html.spec.whatwg.org/multipage/form-elements.html#attr-button-command), and on [CSS Tricks](https://css-tricks.com/invoker-commands-additional-ways-to-work-with-dialog-popover-and-more/). 

### Up and Coming ARIA
{: tabindex="-1"}

I appreciated “[Up and Coming ARIA](https://webaim.org/blog/up-and-coming-aria/)” by John Northup, which shares about some new and notable ARIA attributes and roles and --- importantly --- shares about their current support. I especially appreciated the demo page with examples that’s linked to at the end of the article. Demo pages for this sort of thing are excellent because it helps me to better understand how these attributes may work in practice, to test out support, and (if we have support) understand what the new experience will be like for users of assistive tech.

### ARIA Notify?
{: tabindex="-1"}

Here’s another cutting-edge thing to keep on your radar: ARIA Notify, an API that developers can use to send alert messages to screen reader users. Think of it as an alternative to ARIA live regions. It looks like it’s available as a developer trial in Microsoft Edge. For more, see “[Creating a more accessible web with Aria Notify](https://blogs.windows.com/msedgedev/2025/05/05/creating-a-more-accessible-web-with-aria-notify/)” on the Windows blog. 

This makes sense to me. Currently if you want to give screen reader users this type of live alert message, ARIA live regions are the only way to do it. They can work well for this sort of thing, but there are some limitations and awkwardness to them, and there is something about an API alternative here that feels appropriate to me. 

That said, I am also uneasy about this. I’m uneasy about it because I haven’t seen word of it (or support of it) elsewhere. Don’t use this until it is well-supported by browsers and assistive technologies. I’m also uneasy because I can see this complicating accessibility testing and reporting, although that’s a smaller and more manageable challenge.

ARIA live regions are not perfect, but I think our main problem here is that we have too many people who are building websites who don’t know what ARIA live regions are or understand how to use them appropriately. The ARIA Notify might help with this (it could definitely simplify things in some cases), but the responsibility remains with us web-builders to learn about and practice inclusive and accessible design and development. To that end, if you aren’t confident with ARIA live regions, I highly recommend “[Accessible notifications with ARIA Live Regions](https://www.sarasoueidan.com/blog/accessible-notifications-with-aria-live-regions-part-1/)” by Sara Soueidan.

Tangential: Nic Chan has a super cool website/blog at [nicchan.me](https://www.nicchan.me/) which does an impressive job integrating accessibility into a unique (delightfully retro) design. Check it out! In particular, Nic’s post “[Please, can we have ARIA Notify](https://www.nicchan.me/blog/please-can-we-have-aria-notify/)” dives into this topic in more detail.

### HTML & CSS Tip of the Week
{: tabindex="-1"}

Want to stay up-to-date with new HTML and CSS things and perhaps learn about some useful old things? Check out Kevin Powell’s [HTML & CSS Tip of the Week](https://html-css-tip-of-the-week.netlify.app/). I’ve been following and really enjoying this blog. Add it to your RSS reader!



## WCAG in Plain English
{: tabindex="-1"}

Check out [WCAG in Plain English](https://aaardvarkaccessibility.com/wcag-plain-english/)! It breaks down the Web Content Accessibility Guidelines (WCAG) into plain language.

I’ve come across other similar breakdowns of WCAG before. This is probably my favorite one I’ve seen. I think it generally does a good job at a hard task. What I like about it is that it doesn’t just give you a one-sentence equivalent for each success criterion. Instead, if you follow the “View Details” links, it also has a full page for each success criterion, explaining it approachably in some more detail. It is missing things. Don’t think you can substitute this for [the real thing](https://www.w3.org/WAI/WCAG22/quickref/). But I do think this is a good starting point for people that can help make WCAG practical, concrete, and actionable.

## HTML for the people!
{: tabindex="-1"}

HTML is a delight. So is <htmlforpeople.com>. Please go check it out, especially if you aren’t comfortable with HTML or don’t consider yourself a tech person. It’s a fun, accessible, and approachable introduction to HTML (that is, the web!). Here’s how it starts:

> I don’t think websites were ever intended to be made only by “web professionals.” Websites are documents at heart. Just about everyone knows how to make a document in this digital age, be it Word, Google Docs, Markdown, or something else. HTML shouldn’t be an exception. Sure it’s a bit more technical than other types of documents, but it’s also very special.

HTML is a markup language --- it’s right there in the name: Hypertext Markup Language. A markup language is *not* a programming language. You do *not* have to be a programmer to write HTML. There are a lot of benefits to learning how to write HTML. Accessibility is just one of those. Say it with me: HTML is for the people!

Shout out to Blake Watson for creating <htmlforpeople.com>. [Blake’s website](https://blakewatson.com/) has some excellent pages about assistive tech and accessibility, and I also think Blake’s other projects [A Fine Start](https://afinestart.me/) and [d20 dice roller](https://d20app.me/) are pretty cool. Check ‘em out!

## Error messages that are actually helpful
{: tabindex="-1"}

I appreciated “[How to write error messages that actually help users rather than frustrate them](https://piccalil.li/blog/how-to-write-error-messages-that-actually-help-users-rather-than-frustrate-them/)” by Amy Hupe. I’ve seen a lot of error messages that are really poorly written, and this post has good advice and examples for how to make error messages clear and helpful to everyone. If you make error messages, please read this.

## The Remediation Gap
{: tabindex="-1"}

I appreciated “[Mind The (Remediation) Gap](https://www.tpgi.com/mind-the-remediation-gap/) by Doug Abrams. 

This resonated a lot with me from my time working as an accessibility consultant. There are indeed a lot of “front-end” developers who work nearly exclusively in JavaScript frameworks without a strong foundation in HTML and CSS. Meanwhile, many accessibility testers and consultants focus on vanilla HTML and CSS and can struggle to provide detailed recommendations that are specific to JavaScript frameworks the developers are working in. Moreover, testers and consultants don’t typically get access to the full source code behind the website, only the final output that users access. The remediation gap is real.

Front-end developers need genuine skills with HTML, CSS, and ARIA, and they need to understand the accessibility implications of their JavaScript frameworks. Meanwhile, testers and consultants ought to seek to better understand how websites are coded and give more relevant recommendations. This is everyone’s responsibility.

## Documentation as a strategy
{: tabindex="-1"}

I liked “[If you answer it twice, make it an article](https://www.last-child.com/if-you-answer-it-twice-make-it-an-article.html)” by Ted Drake. Documentation is important. On-demand resources and job-aids can be essential, especially for digital accessibility, something that everyone needs to know about but which can be complicated and technical. I think having a helpful job-aid available for the specific task you’re trying to do can be really impactful. In my current role, I’m a subject matter expert for my institution, so I’ve been paying particular attention to this and saving extra notes whenever I recommend something to someone. If I find myself recommending something multiple times, that helps me know it deserves to be spotlighted.

## Focus Priming
{: tabindex="-1"}

I appreciated Martin Underhill’s post “[Focus priming](https://www.tempertemper.net/blog/focus-priming).” This is a term that I needed and did not have words for --- and now I do!

For more on the hidden complexities of focus, see my post from last year “[Same-Page Links and Tabindex]({{ site.baseurl }}{% post_url 2024-05-23-Skip-links-and-tabindex %}).”

## Access Trauma
{: tabindex="-1"}

Here’s another term that might be helpful to add to your vocabulary: access trauma. Please read “[Combating Access Trauma](https://sightlessscribbles.com/posts/6617/)” by Robert Kingett for a thoughtful reflection on the concept. If you’re someone with a disability, this concept might resonate with your experience. If you’re able bodied, this post will help you better understand the experiences of people who aren’t.

From an organizational perspective, this post is a good example of how you risk alienating your customers or clients through inaccessible communications. For example, Kingett writes:

> Links were displayed all throughout the email, insisting I check out this page or that page or this other page. I had no drive to click on any of them, at all, thanks to the unlabeled image at the top of the email. [...] As I skimmed the subject lines of emails, one singular thought kept percolating, like a restaurant that always serves burnt toast for some reason. I don’t want to open these because I don’t want to deal with the inaccessibility of the content today.

## AccessAble
{: tabindex="-1"}

AccessAbleUSA is a cool site: [accessableusa.com](https://www.accessableusa.com). It offers detailed accessibility information for different physical locations.

Disability and accessibility are both spectrums rather than binaries. Saying that a certain venue is “accessible” or “ADA compliant” doesn’t necessarily let a disabled person know that the venue will work for them or will accommodate them comfortably. AccessAble helps folks know what to expect by breaking things down into [40 accessibility symbols](https://www.accessableusa.com/access-symbols). These include “Automatic or No Doors at the Entrance,” “Assistive Listening,” and “Gender Inclusive Restroom.” The site also tries to include photos of the location and thoughtful notes about getting inside and getting around a building. Check out [Princeton University on AccessAble](https://www.accessableusa.com/searches?query=Princeton+University) for an example of what this can look like. It’s remarkable, genuinely helpful, and surprisingly common-sense once you see it.

I think AccessAble pairs very nicely with Robert Kingett’s post about access trauma. Kingett writes about being reluctant to attend an open mic (something he genuinely enjoys) because he didn’t know what exactly to expect and wasn’t confident the venue could comfortably accommodate him. If we make this sort of detailed access info widely available, our community members with disabilities can better know in advance if a location works for them and everyone can better know what to expect when heading somewhere new.

## Visited links are weird
{: tabindex="-1"}

You know that norm where links tend to be blue by default and after you visit them they change to purple? That’s actually really weird when you think about it.

It’s weird because it’s using color alone to indicate information, which arguably violates the Web Content Accessibility Guidelines (WCAG) success criterion 1.4.1 Use of Color, and because for privacy reasons, you really don’t have many other options for styling visited links, which you can read about here on MDN: “[Privacy and the :visited selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector).” It’s weird!

Shout out to Niq Bernadowitsch for talking about this weird quirk of the web. I enjoyed Niq’s post “[The Design of Visited Links](https://niqwithq.com/posts/the-design-of-visited-links).

## Tools to check color contrast
{: tabindex="-1"}

I recently came across [contrast.report](https://contrast.report/), a website that you can use to test color contrast ratios to make sure that your foreground text is clearly visible against the background. I like it!

My other favorite tools for testing color contrast are [WebAIM’s contrast checker](https://webaim.org/resources/contrastchecker/) and [TPGI’s Colour Contrast Analyser](https://www.tpgi.com/color-contrast-checker/). contrast.report and WebAIM’s checker work best if you just need to do a quick, one-off test, and the Colour Contrast Analyser is best for professionals who want a dedicated app for this stuff.

I should also note that you can use [Chrome DevTools](https://developer.chrome.com/blog/devtools-tips-5) to check color contrast ratios. Sometimes that’s the best tool for the job because you’re already right there. [Firefox DevTools](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/inspect_and_select_colors/index.html) will similarly show you color contrast ratios, but I think Chrome works a little better for this.

## Hiding/Showing Content Accessibly
{: tabindex="-1"}

I appreciated “[Creating an Accessible Accordion with HTML Description Lists](https://afixt.com/creating-an-accessible-accordion-with-html-description-lists/)” by Karl Groves on the AFixt blog.

In particular, what I like about this example is how it hides/shows the accordion panels. There are a lot of ways to hide content on a webpage, and many of them aren’t accessible. I’ve tested many sites that aim to hide certain elements from all users but which nevertheless leave those elements exposed and available to users of assistive technologies like screen readers. I’d say it’s a common problem.

In short, here’s how the accordion panels are hidden/shown in this example. When the page loads, the accordion panels are present in the DOM but hidden from users with aria-hidden="true" and [CSS display none](https://developer.mozilla.org/en-US/docs/Web/CSS/display). There is one, simple JavaScript event listener here: when users click the accordion control, it toggles aria-hidden between true and false values. Then, there is a CSS rule that uses <code>aria-hidden="false"</code> as part of its selector, and it overrides the CSS <code>display: none;</code> with <code>display: block</code>.

This is a simple and effective approach to hiding content. I like how it only requires one, relatively simple JavaScript event listener. The synergy here between ARIA, CSS, and JavaScript is really nice: with the appropriate CSS in place, all you need to do is toggle the aria-hidden value to effectively and accessibly show/hide content.

## Customization: The Heart & Frontier of Accessibility
{: tabindex="-1"}

I appreciated “[Accessibility preference settings, information architecture, and internalized ableism](https://ericwbailey.website/published/accessibility-preference-settings-information-architecture-and-internalized-ableism/)” by Eric W. Bailey. It’s a thoughtful post about customization and accessibility. Customization truly is an important component of accessibility and I’d even call it a frontier for accessibility. Read this and then go on a walk and think about it.
