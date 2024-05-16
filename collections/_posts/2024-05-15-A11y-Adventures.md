---
SPDX-FileCopyrightText: 2024 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Accessibility Adventures: May 2024"
published: true
date: 2024-05-15 17:07
categories:
- accessibility
tags:
- a11y
- tables
- CSS
- JavaScript
description: "Here's what I've been thinking about in the world of accessibility: tables, semantic css, web components, and more."
image: accessible-trail
toc: true
---

## Supplementing Audio Descriptions

Netflix released an 11-minute [audio featurette](https://www.netflix.com/tudum/articles/all-the-light-we-cannot-see-aria-mia-lorbeti-audio-introduction) to accompany its miniseries <cite>All the Light We Cannot See</cite>. The featurette is specifically for audience members who are blind or have low vision, and it provides detailed descriptions of characters and locations in the series.

I think this is a cool idea and hope we can see more of it. [Audio description](https://www.w3.org/WAI/media/av/description/) is a vital way to make TV shows and movies accessible to people who are blind or have low vision, but it has limitations. With standard audio description, descriptions are inserted into the pauses between dialog, but there may not be long enough pauses to allow for detailed descriptions. Extended audio descriptions pause the video to ensure there is sufficient space for detailed descriptions, but extended audio descriptions may not always be practical because they necessitate creating a separate video file or using a specialized video player. I think this audio featurette is a cool idea because it provides a higher level of detail to people who are blind and have low vision without the complexity of extended audio descriptions (and without creating a separate experience for the audience in the way that can happen with extended audio description).

## Running Accessibility Programs

Here's a few resources I've come across or referenced lately that might be helpful to those of you administering or implementing accessibility at the program-level:

* [Digital Accessibility as a Business Practice: Essential Skills for Business Leaders](https://pressbooks.library.torontomu.ca/dabp/), a free ebook created by The Chang School, Toronto Metropolitan University
* [The Book on Accessibility](https://www.thebookonaccessibility.com/) by Charlie Triplett (what it sounds like)
* [MagentaA11y](https://www.magentaa11y.com): tests that you can give your QA folks to make sure that they are testing for accessibility (accessibility acceptance criteria)
* "[How to start your agency’s digital accessibility program](https://adhocteam.us/2024/01/04/OMB-a11y/)" by Brian DeConinck (for those of you working in government)

## Text Over Images

Hannah Milan published two posts on <cite>Smashing Magazine</cite> that are an excellent deep dive into how to accessibly design text over images.

Designers, read this. Accessibility consultants, bookmark this.

1. [Designing Accessible Text Over Images: Best Practices, Techniques, And Resources (Part 1)](https://www.smashingmagazine.com/2023/08/designing-accessible-text-over-images-part1/)
2. [Designing Accessible Text Over Images: Best Practices, Techniques And Resources (Part 2)](https://www.smashingmagazine.com/2023/08/designing-accessible-text-over-images-part2/)

## Tables: Heuristics, Headers, Interactivity, and Responsiveness 

Did you know that browsers use heuristics to determine if your <code>&lt;table&gt;</code> element is actually a logical data table or if it is a layout table?

In general, avoid using native HTML table elements for layout. Instead, use CSS. (Flexbox and Grid are awesome.) But if for some reason you are stuck with a layout table, add <code>role="presentation"</code> to the <code>&lt;table&gt;</code> element and convert any <code>&lt;th&gt;</code> cells to <code>&lt;td&gt;</code> cells. This way, screen readers will not announce a role of table, which is good because layout tables are not logical tables.

However, even if you don’t add <code>role="presentation"</code> to the <code>&lt;table&gt;</code> element, browsers might still judge that your table is a layout table and treat it as such. I think this is because historically way too many people improperly used <code>&lt;table&gt;</code> elements for layout purposes. You can see for yourself: check out the <a href="https://html.spec.whatwg.org/multipage/tables.html#the-table-element">HTML specification for <code>&lt;table&gt;</code> elements</a>:

> User agents, especially those that do table analysis on arbitrary content, are encouraged to find heuristics to determine which tables actually contain data and which are merely being used for layout.

This browser behavior can be a good thing: if a web designer used a layout table but did not mark it as such, screen readers may still treat it as a layout table anyway, which can help out users.

But there are edge cases where this can cause problems. For example, one of my coworkers came across an instance where a logical data table using native HTML table elements was nonetheless judged to be a layout table by Chrome! This was a problem because even though the table was coded appropriately, screen reader users wouldn’t be able to interact with it as a table. If you have a logical data table that’s properly coded but in practice the browser (in the accessibility tree) and screen readers don’t treat it as a table, that’s probably what’s happening: the browser’s internal heuristics are improperly judging it to be a layout table.

You can check the HTML spec for some indicators browsers may use to determine whether a <code>&lt;table&gt;</code> element is in fact a logical data table, and you can check browsers’ source code to determine the exact heuristics. For example, here are [the heuristics WebKit uses](https://github.com/WebKit/WebKit/blob/main/Source/WebCore/accessibility/AccessibilityTable.cpp).

Moving on, hopefully you never have to encounter [complex data tables with multi-level headers](https://www.w3.org/WAI/tutorials/tables/multi-level/) — and please do everything possible to avoid creating these yourself — but if you do find yourself facing one of these and you are using the JAWS screen reader, here is a keyboard command you should know: Ctrl + Alt + 5 on the numeric keypad will announce the headers for the current cell. More information here: <https://webaim.org/articles/jaws/tables.htm>.

Moving on, lately I have come across a few tables that were interactive and included expandable rows. This is complicated stuff! If you have something that is table-like and interactive, you may want to follow the [ARIA grid pattern](https://www.w3.org/WAI/ARIA/apg/patterns/grid/). There are definitely good use cases for it, but it is complex and easy to mess up, so I would encourage you to avoid it if you can. On that point, Adrian Roselli has a helpful post for you: “[Don’t Turn a Table into an ARIA Grid Just for a Clickable Row](https://adrianroselli.com/2023/11/dont-turn-a-table-into-an-aria-grid-just-for-a-clickable-row.html).” If you have a table with expandable/collapsible rows, however, consider using following the [ARIA treegrid pattern](https://www.w3.org/WAI/ARIA/apg/patterns/treegrid/). This is a pattern that I overlooked until recently, but which is actually pretty cool.

Moving on, let’s talk about responsive tables! It may be a good idea to make sure your table can reflow on smaller screens so that users don’t need to constantly scroll left and right to read it. But how exactly can you do that? Fortunately, I’ve got two good resources for you:

* “[How to create a responsive HTML table](https://www.youtube.com/watch?v=czZ1PvNW5hk)” by Kevin Powell (YouTube video)
* “[A Responsive Accessible Table](https://adrianroselli.com/2017/11/a-responsive-accessible-table.html)” by Adrian Roselli

## Math!

I want to quickly signal boost "[Making Math Accessible](https://www.tpgi.com/making-math-accessible/)" by Ricky Onsman, which is a nice intro to making math accessible in HTML content.

## ARIA Live Regions

Screen readers will announce changes in ARIA live regions as they happen without shifting keyboard or screen reader focus. For this reason, ARIA live regions can be an important and helpful way to help make dynamic web content more accessible to screen reader users. Live regions are simple to get started with (<code>aria-live="polite"</code> will do it), but they can get complicated or be tricky to get right. Sara Soueidan has two terrific posts explaining what ARIA live region are and how they work. In particular, Souedian does a great job explaining the lesser-used attributes aria-relevant, aria-atomic, and aria-busy and explaining the lesser-known HTML <code>&lt;output&gt;</code> element. I highly recommend:

* [Accessible notifications with ARIA Live Regions (Part 1)](https://www.sarasoueidan.com/blog/accessible-notifications-with-aria-live-regions-part-1/)
* [Accessible notifications with ARIA Live Regions (Part 2)](https://www.sarasoueidan.com/blog/accessible-notifications-with-aria-live-regions-part-2/)

## Invented and Multiple Roles

Did you know that you can specify multiple values for an element's role attribute? An element can't have more than one role, mind you, but the idea here is that if the first role listed is new and unsupported, assistive technologies should fallback to announcing the secondary role. It's a cool idea, but unfortunately, the support for it isn't great. You can read more here: "[Notes on use of multiple ARIA role attribute values](https://www.tpgi.com/notes-on-use-of-multiple-aria-role-attribute-values/)" by Steve Faulkner.

You can also just straight-up make up roles using the [aria-roledescription](https://www.w3.org/TR/wai-aria-1.2/#aria-roledescription) attribute, which I find wild. That said, I struggle to see any good reasons to use it beyond perhaps <code>aria-roledescription="slide"</code> for slides in a presentation or carousel. (That said, please just avoid carousels.) It's interesting though! You can read more here: "[Avoid aria-roledescription](https://adrianroselli.com/2020/04/avoid-aria-roledescription.html)" by Adrian Roselli.

## Semantic CSS

Accessibility professionals often talk about the importance of “semantic HTML.” For example, if you have a heading, please use a heading element, such as an <code>&lt;h1&gt;</code>. If you instead style a <code>&lt;div&gt;</code> element to look like a heading, screen reader users won’t be able to efficiently navigate the page.

But we can talk about semantic CSS too! For example, if you want to style how a selected tab looks, use <code>[role="tab"][aria-selected="true"]</code> as your CSS selector, not <code>.tab-selected</code>. This way, to achieve the desired look, you’ll need to ensure you’re using semantic HTML. Your tab will look the way it should only if it also communicates the proper role and state to assistive technology users. It’s a more equitable experience since if it’s broke for one class of users, it’s broke for everyone. This also makes it easier to spot bugs in your code, and you won’t need to clutter up your HTML with redundant classes.

Here are some good resources I’ve come across on the topic:

* "[How to write Semantic CSS](https://www.youtube.com/watch?v=lWu5zf_S9R4)" by Kevin Powell (YouTube video)
* "[Style with Stateful, Semantic Selectors](https://benmyers.dev/blog/semantic-selectors/)" by Ben Myers
* "[User Facing State ](https://css-tricks.com/user-facing-state/)" by Scott O'Hara
* "[Using CSS to Enforce Accessibility](https://adrianroselli.com/2021/06/using-css-to-enforce-accessibility.html)" by Adrian Roselli

## JavaScript for Keyboard Accessibility

When we talk about the details of web accessibility, we often talk about HTML (including ARIA) and sometimes CSS comes up as well, but JavaScript doesn't always get the attention or detail it deserves. So here are a few JavaScript-focused resources that relate to keyboard accessibility:

* "[A Guide To Keyboard Accessibility: JavaScript (Part 2)](https://www.smashingmagazine.com/2022/11/guide-keyboard-accessibility-javascript-part2/)" by Cristian Díaz
* [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/): Specifically, check out the Keyboard Interaction section for each pattern and the JavaScript used for the various examples. See also [Developing a Keyboard Interface](https://www.w3.org/WAI/ARIA/apg/practices/keyboard-interface/).
* [Buttons, Enter, and Space]({{ site.baseurl }}{% post_url 2022-12-29-A11y-Adventures %}/#buttons-enter-and-space) from my earlier post "Accessibility Adventures: December 2022"

## Web Components & Shadow DOM 

Speaking of JavaScript, let's talk about web components!

There comes a time in every accessibility consultant's journey in which they become fascinated with and driven to learn about web components and the shadow DOM --- or at least, I’ve hit that point! I still have a ton to learn here, but I know a lot more than I did a year ago. Here are some resources that I’ve found helpful:

* "[Web Components Accessibility FAQ](https://www.matuzo.at/blog/2023/web-components-accessibility-faq/)" by Manuel Matuzović
* "[Pros and cons of using Shadow DOM and style encapsulation](https://www.matuzo.at/blog/2023/pros-and-cons-of-shadow-dom/)" by Manuel Matuzović
* "[How Shadow DOM and accessibility are in conflict](https://alice.pages.igalia.com/blog/how-shadow-dom-and-accessibility-are-in-conflict/)" by Alice Boxhall
* "[Getting into web components - an intro](https://utilitybend.com/blog/getting-into-web-components-an-intro/)" by Brecht De Ruyte
* "[HTML with Superpowers: An Introduction to Web Components](https://htmlwithsuperpowers.netlify.app/)" by Dave Ruper

***

What have you been encountering and thinking about lately in the world of accessibility?
