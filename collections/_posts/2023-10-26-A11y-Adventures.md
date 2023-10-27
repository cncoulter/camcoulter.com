---
SPDX-FileCopyrightText: 2023 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Accessibility Adventures: October 2023"
published: true
date: 2023-10-26 19:04
categories:
- accessibility
tags:
- a11y
- EPUB
description: "Here's what I've been thinking about in the world of accessibility: certifications, ebooks, precise and unambiguous language, and more."
image: refreshable-braille
toc: true
---

## CPACC + WAS = CPWA

The International Association of Accessibility Professionals (IAAP) offers several different professional certifications. Back in 2021, I became a Certified Professional in Accessibility Core Compentencies (CPACC), and I wrote a blog series on this site to help me study for it: [100 Days of A11y]({{ site.baseurl }}/Blog/Tags/#100+Days+of+A11y). Recently, I earned another certification from IAAP: Web Accessibility Specialist (WAS)!

CPACC is more of a generalist, non-technical certification. It's appropriate for all sorts of people whose roles touch on either digital or physical accessibility. Perhaps you are involved in setting policy, perhaps you work with various customers or clients, or perhaps you create things for people to use --- the CPACC certification is relevant for all of those roles.

WAS on the other hand is a technical certification focused specifically on web accessibility. It's appropriate for folks who design, build, or test web content. The WAS exam is broken into three domains: creating accessible web content, testing (or auditing) web content for accessibility issues, and fixing (or remediating) inaccessible web content.

If you have both CPACC and WAS, IAAP gives you a third certification "for free": Certified Professional in Web Accessibility (CPWA). Basically, instead of listing CPACC *and* WAS after my name in my email signature, I can just list CPWA instead. When IAAP sent me an email letting me know that I've become a CPWA, they wrote, "We welcome you to a select group of 664 IAAP CPWAs around the world!" So that's pretty cool! There are less than one thousand of us worldwide, at least so far.

I thought about doing another 100 Days of A11y blog series while I studied for WAS, but I decided against it. The two exams test for different types of knowledge and capabilities. CPACC focuses more on general knowledge about a relatively clearly defined set of topics: different types of disabilities, assistive technologies, the principles of accessibility, and relevant law and policy. For CPACC, it made sense to blog my way through the exam's body of knowledge, explaining each concept in my own words. But WAS is a different beast. WAS tests your knowledge of web development, ARIA, and the Web Content Accessibility Guidelines (WCAG). WAS is less a test of your *knowledge* of these things and more a test of your *skills* at doing these things (creating accessible web content, auditing, remediating). True, I could still have blogged my way through, trying to explain the various concepts that come into play, but doing so felt a bit like going down a rabbit hole to me, and it wasn't clear how in-depth my posts should have gone. How much of HTML and CSS should I explain? How much of ARIA? Does each WCAG success criterion get its own blog post, or should I split it up into four posts (one for each principle)? Moreover, as I said, WAS is more a test of your skill at *doing* things, rather than knowing things. And I have been blessed to have a full-time job at Level Access doing exactly these things alongside well-informed experts for over a year. It was that experience, more so than any of my formal test prep, that prepared me to pass the WAS exam and become a CPWA.

## EPUB Accessibility

EPUB is a file type, similar to DOC or PDF. It's the open standard for ebooks, and it's recently been updated! EPUB 3.3 became a W3C Recommendation (a finalized standard, essentially) in May, along with two other documents specific to EPUB accessibility:

* [EPUB 3.3](https://www.w3.org/TR/2023/REC-epub-33-20230525/)
* [EPUB Accessibility 1.1](https://www.w3.org/TR/2023/REC-epub-a11y-11-20230525/)
* [EPUB Accessibility Techniques 1.1](https://www.w3.org/TR/2023/NOTE-epub-a11y-tech-11-20230519/)

As someone who cares about ebooks, open standards, and accessibility, I find this exciting!

EPUBs are essentially "websites in a box," built using the same technologies as the web (principally HTML and CSS). Therefore, you will notice that EPUB accessibility builds on the Web Content Accessibility Guidelines (WCAG). The new EPUB standard has a [section on accessibility](https://www.w3.org/TR/2023/REC-epub-33-20230525/#sec-accessibility), which states in part:

<blockquote>
<p>The requirements and practices for creating accessible web content have already been documented in the W3C's Web Content Accessibility Guidelines (WCAG) [wcag2]. These guidelines also form the basis for defining accessibility in EPUB publications.</p>
<p>As the current WCAG guidelines (version 2) are heavily focused on web pages, a separate specification, EPUB Accessibility [epub-a11y-11], defines how to apply the standard to EPUB publications. It also adds EPUB-specific requirements and recommendations for metadata, pagination, and media overlays.</p>
</blockquote>

Additionally, the EPUB Accessibility 1.1 specification has a section on [conformance reporting](https://www.w3.org/TR/epub-a11y-11/#sec-conf-reporting). If you are looking to make claims about how well your ebooks conform to the EPUB Accessibility standard, be sure to read that section.

For more on this, you can check out:

* [W3C: EPUB 3.3 becomes a W3C Recommendation](https://www.w3.org/press-releases/2023/epub33-rec/)
* [Fondazione LIA: The new W3C standards for e-books: EPUB 3.3 and EPUB Accessibility 1.1](https://www.fondazionelia.org/en/research-and-development/new-w3c-standards-for-e-books-epub-3-3-and-epub-accessibility-1-1/)

## Watching our language

Adrian Roselli has a series of blog posts that I love:

* "[Stop Using ‘Drop-down’](https://adrianroselli.com/2020/03/stop-using-drop-down.html)"
* "[Stop Using ‘Pop-up’](https://adrianroselli.com/2021/07/stop-using-pop-up.html)"
* "[Be Careful Using ‘Menu’](https://adrianroselli.com/2023/05/be-careful-using-menu.html)"

The terms "drop-down," "pop-up," and "menu" are common and well-understood. The trouble is, they are also vague and ambiguous. It is fine enough for laypeople to use these terms in casual conversation, but web designers, developers, and accessibility professionals need to be more mindful with our language here. Each of these terms can correspond to several different HTML elements, ARIA roles, and design patterns, each with different purposes and uses. If a designer uses the term "pop-up" to refer to a modal dialog, but the developer thinks they mean a new window, the user experience (and likely accessibility) will suffer. I agree with Adrain Roselli: professionals in this space should beware using these terms and make sure they are being as clear and specific as possible, and if you encounter someone using these terms, consider asking them to resolve their ambiguity.

## ARIA Comboboxes and HTML Datalists

When I am testing websites and I notice a combobox, I think, "There's an issue," even before I've found any issues --- because I almost inevitably find issues with them. If you need to make one, I would suggest you carefully reference the [combobox pattern](https://www.w3.org/WAI/ARIA/apg/patterns/combobox/) in the ARIA Authoring Practices Guide and then test it extensively.

Part of what makes comboboxes so error-prone is that they are necessarily custom components --- there isn't a widely-supported native HTML element that fulfills the same function. Native controls are almost always the preferred choice from an accessibility perspective, and here there isn't one.

But that's changing. The native HTML [&lt;datalist&gt; element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist) is getting better support, and it provides a native HTML method to provide a list of recommendations to accompany an input field. It is not going to work for all use cases, and it still has some support limitations and accessibility concerns, but it is starting to become a viable alternative for certain cases. There were a couple blog posts about this recently that I appreciated:

* ["Datalist over ARIA combobox" on Web Axe](https://www.webaxe.org/datalist-over-aria-combobox/)
* ["Under-Engineered Comboboxen?" by Adrian Roselli](https://adrianroselli.com/2023/06/under-engineered-comboboxen.html)

The &lt;datalist&gt; element still has a ways to go, but I see so many issues with ARIA comboboxes, I think more people should start to consider &lt;datalist&gt; as an alternative for their site.

## Sticky Focus & Focus Styles

Here's one thing that pains me: a site with great focus indicators and a sticky header (or footer) that obscures those focus indicators. This is actually something I touched on in my last Accessibility Adventures post ([Focusing on Sticky Headers]({{ site.baseurl }}{% post_url 2022-12-29-A11y-Adventures %}/#focusing-on-sticky-headers)). It's a usability issue that violates the spirit of, although not necessarily the letter of, WCAG SC 2.4.7 Focus Visible. However, there is a new success criterion in WCAG 2.2 that this behavior can clearly violate: [SC 2.4.11: Focus Not Obscured (Minimum) (Level AA)](https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum.html). I am excited to see this new success criterion being added because, as I said, this issue pains me.

So how do you make sure this doesn't happen? Avoid sticky headers and footers. Personally, I hate them. But if you must use one, remember to take keyboard focus into consideration as you build it. Here's one way to ensure your sticky headers don't obscure keyboard focus: "[Sticky content: focus in view](https://tetralogical.com/blog/2023/06/08/focus-in-view/)" by Joe Lamyman.

Relatedly, Joe Lamyman had a recent post titled "[Foundations: visible focus styles](https://tetralogical.com/blog/2023/01/13/foundations-visible-focus-styles/)," which I also appreciated. Focus styles are foundational to keyboard accessibility, and they are also a design element that too often gets overlooked, so please, remember to take keyboard focus indicators into account!

## Pointer Gestures

When I tell people I work in digital accessibility, one of the first things to come up is alt text for images. Many people have heard of that, even folks who otherwise don't know much about accessibility. Alt text gets a lot of attention. That's good.

But you know what doesn't get enough attention? Pointer gestures. When I worked with folks with intellectual and developmental disabilities, a good chunk of them had limited dexterity. Clicking a button with a mouse or tapping a button on a touchscreen could pose a real challenge, and successfully dragging content, using multi-finger gestures, or following a specific path with their finger or a mouse could be real blockers. I understand these types of gestures are less common than images, so it makes sense that alt text gets more press than pointer gestures, but I was happy to come across "[Foundations: pointer gestures](https://tetralogical.com/blog/2023/03/17/foundations-pointer-gestures/)" by Graeme Coleman, which is a great introduction to this topic. When designing pointer gestures, remember to account for folks with limited dexterity.

## Styling Alt Text (and Disabling Images)

That said, let's give alt text some love for a moment. Remember, alt text is not just for screen reader users. Alt text is also for sighted users in case the image doesn't load. If you're sighted, you've probably encountered this at some point yourself. Perhaps the image's <code>src</code> attribute didn't correctly point to an image, or perhaps you had low bandwidth, preventing images from loading properly.

Did you know you can visually style alt text with CSS? I hadn't thought about this before, but once I saw [this blog post by Terence Eden about styling alt text](https://shkspr.mobi/blog/2023/02/how-to-style-your-alt-text/), I thought, *Of course! Why shouldn't we be able to do this?*

Why style your alt text? You can make it obvious if an image is broken, perhaps for QA purposes or perhaps to signal more clearly to users that alt text is alt text. Perhaps more importantly, you can make sure your alt text is readable and has sufficient text contrast. (Is this a thing we should be testing for in web audits? Making sure alt text has sufficient contrast?)

Don't write this off so easily. Tons of people across the world have low bandwidth, and images (especially high-quality ones) might not load reliably for them. Or, people on metered connections might choose to disable images. Did you know this is a thing people can do? This is a thing I've done. I have a 1 GB/month cell phone data plan. That's usually all I need, but on rare occasion I'll find myself tethering my laptop to my phone for WiFi. When I do this, I might disable images in my web browser, preventing images from loading. This can save a ton of data. Here's how to do that in Firefox:

1. Go to about:config
2. Set "permissions.default.image" to 2

That's all. A value of 1 will load images as usual, and a value of 2 will prevent Firefox from downloading and displaying images. Give it a try!

Relatedly, I recently came across the [Cooper Hewitt Museum's Guidelines for Image Description](https://www.cooperhewitt.org/cooper-hewitt-guidelines-for-image-description/), and I must say: I'm impressed! There's a great level of detail and thoughtfulness here. In particular, I appreciate its sections on how to describe gender and ethnicity. In short, it essentially says to use gender-neutral terms unless gender is clearly performed and/or verifiable. As a nonbinary person, this sounds lovely to me: don't assume gender,  but yeah, mention it if it's clearly performed or verifiable. (There's something about describing gender as "verifiable" that I just love.)

## QR Codes

People who are blind use QR codes, so if you have a QR code on your site, make sure you give it informative alt text, otherwise you risk violating WCAG SC 1.1.1 Non-text Content. Your alt text should indicate the image is in fact a QR code and indicate what it links to.

If you set the QR code as a link, make sure the link text describes where the link goes to, otherwise you risk violating WCAG SC 2.4.4 Link Purpose (In Context).

People who are blind use QR codes, but they might have trouble finding them. If you have a QR code on your site or in person somewhere, make it as large as feasible so that it is easy for someone with visual impairments to scan. Don't rely exclusively on QR codes either. Online, provide a link alongside the QR code, and in person, provide a written URL as an alternative. (This is helpful for people without disabilities as well. I've had many occasions where my phone refuses to recognize a QR code for one reason or another.) If you are using a QR code in meatspace, consider what you can do to make the QR code "pop out," so to speak. For example, maybe put a tangible border around it so that people who are blind can figure out with certainty where it is and how big it is. Consider putting a braille label underneath identifying the QR code and what it links to.

There's more to consider about QR code accessibility than just this, but that's what's come up recently for me. For more about QR code accessibility, I'd recommend this post by Joe Lamyman: "[Accessibility and QR codes](https://tetralogical.com/blog/2022/08/08/accessibility-and-qr-codes/)."

## Information Architecture

Back when I participated in Knowbility's Internet Accessibility Rally (AIR) program, the designer on our team used a big term I wasn't familiar with: information architecture. I thought it was a silly, pretentious phrase at first, but she proved me wrong. The way she redesigned the information architecture of the site we were working on was genuinely impressive. Her design made it extremely clear what was on the site and how to get to each thing. It's important work.

To that point, I appreciated this post by Sarah R. Barrett: "[Your Information Architecture is an Accessibility Problem"](https://medium.com/known-item/your-information-architecture-is-an-accessibility-problem-cd54ae917f8e).

## (Cognitively) Inclusive Design

I want to give a shout out to [Microsoft's inclusive design project](https://inclusive.microsoft.design/). Check out their website; they have quality resources that are approachable for all sorts of people. They first got on my radar thanks to their persona spectrum in their [Inclusive 101 Guidebook](https://inclusive.microsoft.design/tools-and-activities/Inclusive101Guidebook.pdf), which illustrates the spectrum of dis/ability.

Today I want to shout out their resources on cognitive accessibility, a topic that doesn't get the attention is deserves. Their [Inclusive Design for Cognition Guidebook](https://inclusive.microsoft.design/tools-and-activities/InclusiveDesignForCognitionGuidebook.pdf) is cool, and they've got a few other associated resources as well.

***

What do you think about all these links and ideas? Are they new to you or have you come across them before? What have you been noticing and thinking about lately in the world of digital accessibility?
