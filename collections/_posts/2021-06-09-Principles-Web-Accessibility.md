---
SPDX-FileCopyrightText: 2022 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Principles of Web Accessibility"
published: true
date: 2021-06-09 06:31
categories:
- accessibility
tags:
- 100 Days of A11y
description: "What are the main ideas and guiding principles behind web accessibility?"
image: a11y
toc: true
---

## Introduction

What are the main ideas and guiding principles behind web accessibility? How are those principles applied in practice?

First, let's start with some context.

## W3C & WAI

The [World Wide Web Consortium](https://www.w3.org/) (W3C) is the standards organization for the web. Technically, the W3C creates what are called *W3C Recommendations* for web standards, and has [a well-defined process](https://www.w3.org/2020/Process-20200915/#rec-track) for doing so. In short, different working groups are chartered to tackle specific topics. Before a working group's specification is officially published as a W3C Recommendation (REC), it will go through several revisions and stages, including a Working Draft (WD), Candidate Recommendation (CD), and Proposed Recommendation (PR).

The W3C has an initiative called the [Web Accessibility Initiative](https://www.w3.org/WAI/) (WAI) which develops guidelines and standards for web accessibility as well as support materials and other related resources. Personally, I think WAI has a great, informative website filled with helpful resources. Go check it out! Here are the main sections of WAI's website:

1. [Accessibility Fundamentals](https://www.w3.org/WAI/fundamentals/)
2. [Planning and Policies](https://www.w3.org/WAI/planning/)
3. [Design and Develop](https://www.w3.org/WAI/design-develop/)
4. [Test and Evaluate](https://www.w3.org/WAI/test-evaluate/)
5. [Teach and Advocate](https://www.w3.org/WAI/teach-advocate/)
6. [Standards/Guidelines](https://www.w3.org/WAI/standards-guidelines/)

I think the principles behind web accessibility aren't that complex, and I think it can be relatively easy to create an accessible website, provided that your website isn't too complex (and provided you take a proactive approach to accessibility). That said, as a whole, the web is complex, with many separate pieces interacting together, and there are many layers to web accessibility, particularly when you factor in assistive technologies. WAI has a helpful webpage that breaks down these different layers of web accessibility: [Essential Components of Web Accessibility](https://www.w3.org/WAI/fundamentals/components/). Briefly, here's how I break it down: developers and content creators use authoring and evaluation tools to create web content. Then, users access that web content through "user agents," such as web browsers or assistive technologies.

The W3C has created accessibility guidelines for these different components:

1. [Authoring Tool Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/atag/) (ATAG)
2. [Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/) (WCAG)
3. [User Agent Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/uaag/) (UAAG)

The W3C has also published an official W3C Recommendation for [Web Accessibility Initiative – Accessible Rich Internet Applications](https://www.w3.org/WAI/standards-guidelines/aria/) (WAI-ARIA), a technical specification which web designers and developers can use to help create accessible web content and web applications. ARIA is a way to extend HTML so that complicated webpages can work better with assistive technologies.

Additionally, the W3C currently has a working draft of the [W3C Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/wcag3-intro/) (WCAG) 3.0. These guidelines aim to provide a wide range of recommendations for making a wide range of web content accessible to a wide range of users with disabilities on a wide range of user agents and devices. This working draft was formerly referred to as "silver," because silver is referred to as "Ag" on the periodic table, and AG is an abbreviation of "accessibility guidelines."

I think all of that is helpful as context. (I do love context.) Now, let's dig into WCAG, the actual principles of web accessibility, and how we apply those in practice.

## WCAG

The W3C's Web Content Accessibility Guidelines (WCAG) explain how to make web content accessible to people with disabilities. The page "[Accessibility Principles](https://www.w3.org/WAI/fundamentals/accessibility-principles/)" on WAI's website summarizes the principles behind WCAG in fairly approachable language.

The first version of the Web Content Accessibility Guidelines --- WCAG 1.0 --- became an official W3C Recommendation in 1999. WCAG 2.0 superseded it and became a W3C Recommendation in 2008. [WCAG 2.1](https://www.w3.org/TR/WCAG21/) became a W3C Recommendation in 2018 and is the current standard. WCAG 2.1 has additional success criteria that were not included in WCAG 2.0, and it was created to improve accessible for users with cognitive or learning disabilities, users with low vision, and users with disabilities on mobile devices. For more on the updates in WCAG 2.1, see "[What’s New in WCAG 2.1](https://www.w3.org/WAI/standards-guidelines/wcag/new-in-21/)." While WCAG 2.1 is the current standard, there is currently a working draft for [WCAG 2.2](https://www.w3.org/WAI/standards-guidelines/wcag/new-in-22/), and it seems likely that WCAG 2.2 may become an official W3C Recommendation sometime later this year.

WCAG breaks down into four principles, which form the acronym POUR: perceivable, operable, understandable, and robust.

<b>Perceivable</b>. Web content and interfaces must be presentable in ways that users can perceive through sight, hearing, or touch. Digital text is an awesome and revolutionary format because practically anyone can access it. Thanks to screens, screen readers, and refreshable braille displays, you can see, hear, or feel content that is available as digital text. Some people can't see, so make sure that they can still perceive your content through hearing or touch (through digital text). In practice, make sure you have alternative text for images that people using screen readers can access, so that they can get a sense of what the picture is about. Use sufficient color contrast so that people with low vision can still read your content. Allow users to increase the size of text, and to do so without breaking your webpage. If you have a video, provide captions, audio description, and a transcript.

<b>Operable</b>. The components of the user interface must be operable through a variety of input methods. People use many different types of input methods when using computers. While many people use a keyboard alongside a mouse or a trackpad, other people are mouse-only or keyboard-only users or interact through touchscreens or voice recognition. People should be able to interact with your content through any of these input methods. In practice, make sure that all your content is accessible to someone using only a keyboard or only a mouse. Ensure that you have visual focus indicators to assist with keyboard navigation. If you have a session timeout, give people warning and allow them to extend or opt-out of the timeout. (People who use switch devices often require more time to fill out a form.) Avoid flash animations that can cause seizures in some people.

<b>Understandable.</b> Users should be able to understand and comprehend content and interfaces. In practice, make sure you identify (in the page's HTML markup) which language the text is written in, so that screen readers correctly pronounce your text. Use plain language wherever possible to allow more readers to understand your content. Include supporting images, audio, and video to help users understand text content. Create predictable and consistent user interfaces. Give feedback when there are errors or for confirmation of certain actions. Provide context, hints, and clear labels.

<b>Robust.</b> Web content should be compatible with as many "user agents" as possible, including different types of devices and assistive technologies. It should be robust enough so that all these user agents can interpret it reliably. In practice, use valid, accurate, and semantic markup, and extend HTML with ARIA where appropriate.

Perceivable, operable, understandable, and robust: those are the four high-level principles of WCAG. Those four principles break down into 13 guidelines in WCAG 2.1. For example, under "[Principle 1 --- Perceivable](https://www.w3.org/TR/WCAG21/#perceivable)," we have "[Guideline 1.1 --- Text Alternatives](https://www.w3.org/TR/WCAG21/#text-alternatives)." This guideline states:

> Provide text alternatives for any non-text content so that it can be changed into other forms people need, such as large print, braille, speech, symbols or simpler language.

Those 13 guidelines in WCAG 2.1 are then broken down into 78 testable success criteria. The guidelines and success criteria of WCAG are "normative," meaning they are required for conformance. Here is an example of a testable success criterion: under the text alternatives guideline, we have "[Success Criterion 1.1.1 Non-text Content](https://www.w3.org/TR/WCAG21/#non-text-content)," which reads:

> All non-text content that is presented to the user has a text alternative that serves the equivalent purpose, except for the situations listed below.

Success Criterion 1.1.1 goes on to list a few special exceptions. For example, images that are purely decorative do not require text alternatives if they are given an empty alt attribute so that they may be ignored by assistive technologies.

Each success criterion is also associated with a level: A, AA, or AAA. WCAG has three different conformance levels. Level A is the minimum level of conformance, level AA is the de facto standard and norm, and level AAA is the optimal or ideal level of conformance, going "above and beyond" in some ways. Success criterion 1.1.1, for example, is associated with level A. You must meet this criterion to conform with any level of WCAG. To conform to WCAG 2.1 level AA, you'll need to meet all success criterion associated with level A and level AA. To conform to WCAG 2.1 level AAA, you'll need to meet all 78 success criteria.

If you're already familiar with WCAG and need a quick reference, the W3C has you covered: "[How to Meet WCAG (Quick Reference)](https://www.w3.org/WAI/WCAG21/quickref/)."

The W3C also has a guide to [understanding and implementing WCAG](https://www.w3.org/WAI/WCAG21/Understanding/) and a collection of [techniques and common failures](https://www.w3.org/WAI/WCAG21/Techniques/). Note: these two resources are informative, not normative. (They provide guidance and are not required for conformance.)

Mozilla's [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG) has a section on understanding WCAG that I think is also a helpful resource.

One last note: while the principles, guidelines, and success criteria of WCAG were created to apply specifically to *web* accessibility, you can also apply these ideas to digital technology or information and communications technology (ICT) more generally. For example, let's say you are creating a digital kiosk for an airport. Is the content perceivable to people with different disabilities? Can people use different input methods to interact with it and operate it? Are the interface and content understandable to a wide variety of individuals?
