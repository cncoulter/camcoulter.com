---
SPDX-FileCopyrightText: 2022 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Accessibility Adventures: December 2022"
published: true
date: 2022-12-29 19:40
categories:
- accessibility
tags:
- a11y
- ARIA
- buttons
- Fedora
description: "Here's what I've been thinking about in the world of accessibility: buttons, ARIA, iOS, Android, Fedora, and more."
image: refreshable-braille
toc: true
---

## Introduction

A lot has changed since [my last Accessibility Adventures post back in November 2021]({{ site.baseurl }}{% post_url 2021-11-11-A11y-Adventures %}). For one thing, I finished a [redesign of my personal website/blog]({% post_url 2022-09-12-Website-Redesign %}). For another, I transitioned into a full-time accessibility role: I now work as a Senior Accessibility Analyst at Level Access, where I test websites and apps to make sure they work well for people with disabilities and people who use assistive technologies such as screen readers. I've generally been quite happy with this role, and I have been able to learn *a lot* about digital accessibility.

For example, I remember a year ago I understood what the Accessible Rich Internet Applications (ARIA) specification was, but I wasn't comfortable reading the specification, using it, or testing ARIA components. Now, I am routinely flagging accessibility issues that relate to ARIA, looking up specific ARIA design patterns, and making recommendations for complex web components that involve ARIA. There is still a lot I can and want to learn about ARIA (and web accessibility in general), but I now have significantly more practical experience alongside a robust understanding of the technical details of web accessibility.

Now, with that preamble out of the way, let's talk about some of the cool accessibility things I've come across recently.

## ARIA Authoring Practices Guide (APG)

Since I just mentioned ARIA, let's start with the [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/) (APG). This summer, it was updated and released with a spiffy new website. This existed before, but it looked more like a typical technical specification and wasn't nearly as engaging or user-friendly.

The APG is amazing. It is well-designed, and it clearly presents wonderfully helpful information. Basically, if you are trying to develop any sort of interactive web component (like a accordions, tabs, comboboxes, etc), come read and reference the APG early in your development. It lists expected and helpful keyboard interaction patterns as well as expected ARIA roles, states, and properties. It also features working and accessible examples of these components, and this is all presented in a user-friendly, approachable way.

## Buttons, <kbd>Enter</kbd>, and <kbd>Space</kbd>

I'm a little obsessed with Adrian Roselli's blog post "[Brief Note on Buttons, Enter, and Space](https://adrianroselli.com/2022/04/brief-note-on-buttons-enter-and-space.html)."

Online, as a keyboard user, you can press either <kbd>Enter</kbd> or <kbd>Space</kbd> to activate a button. But (with native controls at least), it's actually more complicated than that. Native buttons fire on key down when you press <kbd>Enter</kbd>. That means you can hold down the <kbd>Enter</kbd> key to repeatedly activate the button. On the other hand, native buttons fire on key up when you press <kbd>Space</kbd>. That means you can press down <kbd>Space</kbd> with your right hand, realize you actually don't want to activate the element, and then press <kbd>Tab</kbd> with your left hand to shift keyboard focus away from the button without activating it. Both of these options are useful — sometimes you may want to repeatedly activate a button, and other times you may want to be able to change your mind and not activate it after all. This is made even more complicated with screen readers. Typically, when screen reader users press either <kbd>Enter</kbd> or <kbd>Space</kbd>, screen readers actually fire click events, rather than keyboard events. I think this behavior is because many buttons are not keyboard accessible, so by firing click events, screen readers can activate more buttons and therefore be more useful to blind users.

I find this fascinating because this sort of minutia is easily unknown and overlooked, but it has significant implications. It is important to keyboard users because even though both <kbd>Enter</kbd> and <kbd>Space</kbd> will activate a button, they do so in different ways and therefore aren't interchangeable. While only a minority of folks are keyboard-only users, a majority of people use keyboards at least some of the time online, and so this is potentially something most people would benefit from knowing. Beyond that, this is something most developers should know as well. If you are creating custom components on your site, you will need to create event listeners so that users can interact with those components, and if you're doing that, you probably should stick with the established pattern users are familiar with: <kbd>Enter</kbd> fires on key down (potentially repeatedly) while <kbd>Space</kbd> fires on key up. I find this interesting because it's a small thing, but it helps me to understand the web with more nuance and sophistication, and because it can have surprisingly broad implications.

Relatedly, here's another thing I learned recently: native button elements will fire click events when a user clicks on the button but also when keyboard users press <kbd>Enter</kbd> or <kbd>Space</kbd>. This means with a native button element, you only need to write one JavaScript event listener (for a click event) to make the button work for mouse users, touchscreen users, and for keyboard users. However, if you try to use a div element to create a custom button (for example, something like <code>div role="button"</code>), click events for that button will only be triggered when users click — click events won't trigger if users press <kbd>Enter</kbd> or <kbd>Space</kbd>. That means, you'll need to write more JavaScript event listeners to make those custom buttons accessible to both mouse users and keyboard users. Again, I find this interesting because it's a small, technical detail that helps me better understand and explain matters of web accessibility, but also this has broad implications, so broad that I'd think more web developers need to know this (but I'm not confident they do).

## Creating Custom Buttons

I liked Ben Myer's blog post "[How (Not) to Build a Button](https://benmyers.dev/blog/clickable-divs/)." Web developers often create buttons using div elements with click event handlers, but this style of buttons isn't necessarily accessible to keyboard users or assistive technology users. If you're using a div element to create a button, there's a number of additional things you need to do to make sure keyboard users and assistive technology users can actually interact with and use the button: it needs to receive keyboard focus, have a visible focus style, be triggered by click events as well as <kbd>Enter</kbd> and <kbd>Space</kbd>, and it needs to communicate proper role and state information to assistive technologies. Again, these issues are things I come across all the time when I am testing websites. Ben Myer's post is a good explainer about how to clickable div element and turn it into a proper button.

## Labeling Buttons

I liked Manuel Matuzović's blog post "[Buttons and the Baader–Meinhof phenomenon](https://www.matuzo.at/blog/2022/button-baader/)." This blog post is about right and wrong ways to label buttons. When we label a button, we provide it with an accessible name that can be announced via assistive technologies such as screen readers. It's important that we make sure buttons have proper labels so that screen readers users understand what the button does. There are a lot of different ways to label buttons and links, particularly when the button only has an icon and no visible label (which is often the case with search buttons or social media links). Manuel Matuzović's post lists out several different ways you can label a button and several common mistakes. The post is a good learning tool as well as a good resource for all of your options.

## Accessibility in Fedora

I enjoyed reading these articles in <cite>Fedora Magazine</cite>:

* "[Accessibility in Fedora Workstation](https://fedoramagazine.org/accessibility-in-fedora-workstation)"
* "[Your Personal Voice Assistant on Fedora Linux](https://fedoramagazine.org/your-personal-voice-assistant-on-fedora-linux/)"

I am a Fedora user and a digital accessibility professional. I care about free/libre and open-source software and about accessibility, so it's important to me that Fedora and other Linux distributions are accessible, work well for people with disabilities, and include people with disabilities in the community, so I naturally enjoyed reading about what's going on with this all in Fedora.

## iOS and Android Accessibility

Most of my experience and expertise in digital accessibility has been specifically directed toward web accessibility. That's because there's huge demand for web accessibility skills in particular, because I'm personally interested in the web, and because on the web it's easy to inspect the source code to better understand what makes good things good and bad things bad.

But I'm also interested in accessibility on other platforms as well. For example, I want to learn more about document accessibility and Fedora/GNOME accessibility. I have also been learning more about native iOS and Android accessibility and I have started testing native iOS and Android apps. There is a lot that carries over between web accessibility, but there's a lot that's substantially different as well.

To that point, I enjoyed reading "[How to Fix Common iOS Accessibility Issues](https://www.deque.com/blog/how-to-fix-common-ios-accessibility-issues/)" by Jennifer Korth because it dives into some of those things that are different and unique about iOS accessibility.

Similarity, I think "[Principles for improving app accessibility](https://developer.android.com/guide/topics/ui/accessibility/principles)", part of Android's developer documentation, is an interesting read because it explores digitial accessibility principles and practices that are specific to the Android platform.

## Swearing and Speech-to-Text Software

I enjoyed Eric Bailey's blog post "[Swearing and automatic captions](https://ericwbailey.website/published/swearing-and-automatic-captions/)." Many video platforms, automatic captioning services, and speech-to-text services censor curse words. That inappropriately infantilizes users who rely on captioning, presuming they can't handle or use certain words, and it can also lead to confusion in certain contexts. Obviously, swearing may not be appropriate in all contexts, but it isn't the job of captioning services to deem which words are appropriate or to censor those words when users say them. In this blog post, Eric Bailey explains this issue in greater detail and then reports on which speech-to-text platforms inappropriately censor users' speech. It's a fun read on an important topic.

## Annotating Designs for Accessibility

You may have heard of "shifting left" in regard to accessibility. That term refers to the idea that accessibility should be integrated throughout the entire development lifecycle and content creation process, in contrast to treating accessibility as something you can bolt-on after the fact. Shifting left in accessibility is important because by taking a proactive approach to accessibility you can create more accessible end-products with less time and less money.

Part of shifting left entails bringing designers into the accessibility conversation. Designers should pay attention to color contrast requirements, but they have a larger role to play when it comes to accessibility than just that. Designers should also pay attention to labels and accessible names, whether elements are considered decorative or informative, reading order, and elements' roles and states. When designers annotate their designers with this information, it can create less work for other members on their team and help ensure a more accessible result for users.

But how exactly can designers do that? Claire Webber and Sarah Pulis share their answer (and detailed examples) in their presentation [Annotating designs for Accessibility](https://www.youtube.com/watch?v=Y35jmpS8lQM) from Inclusive Design 24. I enjoyed their presentation, and I highly recommend it to anyone working in design. I suspect that "annotating designs for accessibility" will be a much bigger, more commonplace thing in five to ten years from now, if not sooner.

## Focusing on Sticky Headers

You've probably encountered a sticky header before (a header that stays at the top of your screen even when you scroll down the page).

Sticky headers can often present challenges for sighted keyboard users, who rely on focus indicators to identify which element has keyboard focus. A focus indicator is typically an outline that appears around a button or a link when it has keyboard focus; this indicates to keyboard users that if you press <kbd>Enter</kbd>, you can activate the button or link. If sighted keyboard users can't clearly identify which element has keyboard focus, they essentially don't know where they are on the page, and it can be challenging if not impossible to navigate throughout a site or fill out a form. Programmatically, sticky headers often appear "over" other elements on the page, obscuring or hiding the elements behind them, and if developers aren't careful, sticky headers can obscure or hide elements that have keyboard focus. This is especially likely to happen when users press <kbd>Shift</kbd>+<kbd>Tab</kbd> to navigate back up a page. This is an issue I've come across at least a couple of times while testing.

So I was excited to come across "[Prevent focused elements from being obscured by sticky headers](https://www.tpgi.com/prevent-focused-elements-from-being-obscured-by-sticky-headers/)" by James Edwards, which demonstrates how to create an accessible sticky header, one that doesn't obscure keyboard focus for elements behind it. If you're creating a sticky header or footer, make sure you are planning for this!

## HTMHell Advent Calendar

[HTMHell](https://www.htmhell.dev/) is one of my favorite accessibility blogs. [I've shared about HTMHell before]({{ site.baseurl }}{% post_url 2021-11-11-A11y-Adventures %}/#htmhell), back when I first discovered it, and I'm happy to stay HTMHell is still crushing it.

HTMHell published an [advent calendar](https://www.htmhell.dev/adventcalendar/) for 2022, posting 24 articles about accessibility. Here are my favorite posts:

* "[How to transfigure wireframes into HTML](https://www.htmhell.dev/adventcalendar/2022/1/)" by Lara Aigmüller
* "[You Don't Need ARIA For That](https://www.htmhell.dev/adventcalendar/2022/2/)" by Dennis E. Lembrée
* "[Meaningful labels using ARIA – or not](https://www.htmhell.dev/adventcalendar/2022/7/)" by Suzy Naschansky
* "[There can be only one: Options for building “choose one” fields](https://www.htmhell.dev/adventcalendar/2022/11/)" by Aaron Gustafson
* "[One day we'll have a fully customisable select](https://www.htmhell.dev/adventcalendar/2022/13/)" by Hidde de Vries
* "[Common nesting issues in HTML](https://www.htmhell.dev/adventcalendar/2022/20/) by Silvestar
* "[Preventing form submission with zero Javascript](https://www.htmhell.dev/adventcalendar/2022/24/)" by Eric W. Bailey

***

What do you think about all these links and ideas? Are they new to you or have you come across them before? What have you been noticing and thinking about lately in the world of digital accessibility?

