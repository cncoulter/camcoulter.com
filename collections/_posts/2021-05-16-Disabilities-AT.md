---
SPDX-FileCopyrightText: 2022 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Disabilities, Barriers, Adaptive Strategies, and Assistive Tech"
published: true
date: 2021-05-16 18:10
date_updated: 2021-07-22 19:28
categories:
- accessibility
tags:
- 100 Days of A11y
description: "What are different types of disabilities? What are their characteristics and associated barriers? What are appropriate adaptive strategies, assistive technologies, and social and/or environmental supports?"
image: a11y
toc: true
---

## Introduction

This is a long post with a lot to cover. Let's jump into it!

Our guiding questions are: What are different types of disabilities? What are their characteristics and associated barriers? What are appropriate adaptive strategies, assistive technologies, and social and/or environmental supports?

## Visual Disabilities

Visual disabilities include blindness, low vision, color blindness, and deafblindness.

## Blindness

We often use the term "blindness" to refer to people who entirely lack vision, but the term can also refer to people with extremely limited vision. In the United States, you can qualify as "legally blind" while still retaining some degree of vision.

People who are blind can't read traditionally printed text, and so they may use a program called a [screen reader](https://www.youtube.com/watch?v=5R-6WvAihms) to hear digital content read aloud to them. Screen readers can also output to refreshable braille displays. Many people who are blind actually don't know braille. Feeling braille has several advantages over listening to text: (1) Reading braille explicitly conveys spelling and punctuation, and (2) People can read braille silently, which is helpful in noisy environments, in places where silence is important (like libraries), or when dealing with personal/confidential information.

However, in order for screen readers to work properly, we must create apps, websites, and documents accessibly, in ways that are compatible with assistive technology.

People who are blind can also benefit from digital assistants, like Siri, Alexa, or [Mycroft](https://mycroft.ai/).

Audio descriptions can also be helpful to people who are blind. Audio descriptions are a special audio track in a video, which includes narration describing the visual elements of the video. Many videos unfortunately lack audio description, but audio description is slowly becoming more common. You can stream audio-described TV shows on Netflix and Amazon, for example.

In physical environments, people who are blind can benefit from optical character recognition (OCR) software, which converts pictures into text that screen readers can process. OCR software, such as [Google's Lookout app](https://play.google.com/store/apps/details?id=com.google.android.apps.accessibility.reveal&hl=en_US&gl=US), can help you to identify bills of currency or read labels, for example.

We should also design our built environments so that people who are blind do not need to rely on OCR. Paper bills can be created in different sizes and textures, and we can use braille to make more things readable. We can even use tactile printing technology to create tactile maps.

## Low Vision

People who have low vision may struggle to read text even with corrective lenses. People with low vision often need large text or text with a high color contrast in order to read.

In the digital world, people with low vision may increase the default text size, use screen magnifier software to increase the size of text, or change the colors on screen to create sharper contrast. Similarly, people with low vision benefit when designers create apps, websites, and physical products with large text and sufficient color contrast. People with low vision may also use screen readers and text-to-speech (TTS) software to listen to digital content. Additionally, people with low vision and people who are blind may benefit from speech-to-text (STT) software when writing.

In physical environments, people with low vision may use magnifiers and document cameras.

## Color Blindness

People with color blindness have difficulty differentiating colors.

People with color blindness can use color filters in digital environments and specialized lenses in physical environments to help them differentiate colors. Even better, designers should abstain from using color alone to convey information. For example, use textures or labels in a graph to convey information, or add text or icons on a website in addition to color.

## Deafblindness

People who are deafblind may actually retain some vision or hearing, but in general can not rely on those senses, so touch becomes their primary means of accessing information.

In digital environments, people who are deafblind will typically use screen readers alongside refreshable braille displays. As with people who are blind, it is important that designers and developers create apps, websites, and documents accessibly, in ways that are compatible with screen readers. Additionally, people who are deafblind cannot access audiovisual content, so it is important that we publish descriptive transcripts alongside videos.

In physical environments, people who are deafblind benefit from printed braille. They may also use [tactile signing](https://en.wikipedia.org/wiki/Tactile_signing) to communicate with others.

## Auditory Disabilities

People who are deaf, hard of hearing, and deafblind all have auditory disabilities. People who are deaf generally can't hear anything useful, while people who are hard of hearing do retain some useful hearing but may have significant limitations or impairments.

In general, people who are deaf or hard of hearing benefit from audio content being communicated in other means, such as through sign language or captions. For example, an in-person lecture may have sign language interpretation or live captions projected on a monitor. Android devices have a [live transcribe feature](https://www.android.com/accessibility/live-transcribe/), which allows you to see computer-generated captions on the fly. (Computer-generated transcripts can be prone to mistakes and typically lack punctuation, so it's often helpful to have transcripts created or edited by a human.) Videos should have synchronized captions. (Subtitles only represent spoken words, while captions convey speech as well as sound effects. Closed captions can be toggled on or off, while open captions are permanently burned into a video track.) Descriptive transcripts can also be a helpful supplement to synchronized captions. Alarms like doorbells, which are typically auditory, can instead be visual (a change in lights) or tactile (a vibration).

People who are hard of hearing may use hearing aids. People who are deaf or with significant hearing loss may use cochlear implants, which mimic normal acoustic hearing by directly stimulating the auditory nerve with electric signals.

I think hearing aids and cochlear implants are really interesting pieces of technology, examples of when assistive technology actually surpasses traditional hearing in some ways. People can turn off cochlear implants or take off their hearing aids and experience the calm of silence even in noisy environments. People with hearing aids and cochlear implants can also benefit from [hearing loops systems](https://www.hearinglink.org/living/loops-equipment/hearing-loops/what-is-a-hearing-loop/) (sometimes called audio induction loops). At a play or lecture, for example, someone with a hearing aid can use a hearing loop system to tune in directly to the microphone on stage and tune out the person talking or coughing behind them.

When it comes to distance communication, people who are deaf or hard of hearing can benefit from text messages, teletypewriters (TTYs), and [TTY relay services](https://www.nad.org/resources/technology/telephone-and-relay-services/tty-and-tty-relay-services/). These days, TTYs are somewhat outdated, and [ASL over video online](https://aslnow.com/) is increasingly becoming a more common (and better) way to provide customer service. Online text-based chats can also be helpful.

## Mobility Disabilities

There are many different disabilities that affect mobility. Mobility disabilities can affect both fine motor skills (like fluently using a mouse) and gross motor skills (like moving your arm).

In physical environments, people with mobility impairments may have difficulty moving around or interacting with their environment (for example, opening doors, using faucets, or turning pages). Therefore, people with mobility impairments may also use versions of everyday products that are specially designed to be more ergonomic or accessible. They may also use canes, walkers, or wheelchairs. Relatedly, it's important that physical spaces are designed inclusively: doors and hallways should be wide enough for wheelchair users. Accessible ramps should be provided in addition to stairs. Seating should accommodate a variety of people and body sizes.

In the digital world, there are many different assistive technologies people with mobility impairments might use. First, they may use specially designed keyboards and mouses that are more ergonomic and easier to use. Styluses, head wands, and mouth sticks, often in conjunction with touchscreens, can be helpful to others. Eye-tracking software can allow a user to control a computer with only their eyes, and voice access software can allow a user (who can see the computer screen) to control their device with only their voice. Apple supports [voice control on Mac computers and iOS devices](https://www.youtube.com/watch?v=aqoXFCCTfm4), and Google supports [voice access on Android devices](https://www.youtube.com/watch?v=tXMcDitp3WQ). Even if people with mobility impairments don't use voice access to control their device, they may still use voice recognition software to type.

Additionally, people with mobility impairments may use switch controls to control electronic devices. This technology is sometimes also referred to as switch access or switch devices. A switch control is essentially one or more easy-to-press buttons that users can press to control their device. There are also sip-and-puff switches that function more like using a straw rather than pressing a button. Switch controls are highly configurable; there are many different ways to set them up and use them. Here are two videos that explain switch controls on Android devices:

1. [Switch Access for Android](https://www.youtube.com/watch?v=rAIXE6ilRQ0)
2. [Assistive Tech: Switch Device](https://www.youtube.com/watch?v=V1yoOLhx_qA)

Like with screen readers, in order for switch controls to work properly, software must be designed accessibly, in ways that are keyboard accessible and compatible with assistive technology. Additionally, people with mobility impairments often need more time to complete tasks, so developers should beware session timeouts. They should either turn off time limits or notify users in advance and give them a way to extend or turn off the time limit.

## Speech Disabilities

Speech disabilities can be caused by a broad set of sources, including cognitive, motor, and auditory conditions.

Many people with speech disabilities will use augmentative and alternative communication (AAC) to either supplant or replace traditional oral speech. AAC is a broad term, which breaks down into two main categories: unaided and aided.

If someone uses unaided AAC, they will use their body to communicate but not their voice. For example, they may communicate via gestures, facial expressions, or sign language.

Aided AAC relies on some sort of tool. Basic aided AAC may use pen and paper or printed [communication boards](https://www.healthline.com/health/communication-board), while high-tech aided AAC relies on electronic devices. There are many different types of AAC, and many different types of high-tech aided AAC. Some tools rely on pictures to communicate, while others are alphabet-based and require some degree of literacy. Some high-tech AAC devices use text-to-speech (TTS) software, allowing users to communicate with others via a computer-generated voice.

People with speech disabilities may require more time to communicate and may benefit from text-based alternatives. For example, if a company provides online customer service, it is helpful to provide a text-based chat option in addition to phone or video options. (It is also important to provide an online video sign language option.) Additionally, customer service representatives should be trained on disability etiquette and be patient when supporting persons with speech disabilities.

## Seizure Disabilities

Seizures can be caused by many factors, including fevers, drug withdrawals, and flashing lights. Photosensitive epilepsy is a condition where flashing lights can cause a person to have seizures. For some people, flashing or flickering lights is the only cause of their seizures (pure photosensitivity), while some people with photosensitive epilepsy may also experience seizures caused by other circumstances.

People may take medications to help prevent seizures. Flicker-free monitors and anti-glare glasses can help prevent seizures for some people. Some people who have recurring seizures may carry with them wearable technology that can call for help and send their GPS location in case of seizures.

For the safety of people with photosensitive epilepsy, it is important that video creators and web and app designers limit flashing and strobe-like effects and ideally provide a way to avoid these effects altogether.

## Cognitive Disabilities

The category of cognitive disabilities is incredibly broad and diverse. Not only are there many different types of cognitive disabilities, but many cognitive disabilities affect different people differently, and people with the same condition may not experience all the same symptoms or characteristics.

## Intellectual & Developmental Disabilities

Intellectual and developmental disabilities are also sometimes known as learning disabilities. These disabilities can be congenital or acquired and can affect a person's memory, attention, problem-solving, and/or comprehension. People with developmental disabilities (and other cognitive disabilities) may also have a low tolerance for cognitive overload, causing them to freeze or become upset more easily when there are too many things to process.

Complex sentences with unusual or advanced vocabulary can present barriers to persons with learning disabilities. Complex, cluttered, and distracting layouts can also create barriers, as well as loud or distracting environments.

People with these disabilities can benefit from [plain language](https://www.plainlanguage.gov/), supporting text content with audio and/or video content, and clean and simplified layouts, interfaces, and environments. Text-to-speech (TTS) software can also help people with developmental disabilities to process text content. (And therefore it is important that text content is published accessibly, in ways that are compatible with assistive technologies.)

When communicating, people with developmental disabilities may benefit from AAC, speech-to-text (STT) software, and/or word prediction software.

People with developmental disabilities can also benefit from a wide and creative array of adaptive strategies and assistive technologies that support memory and attention. For example, password managers, PDAs, and speed dial can all help someone with memory challenges.

I want to briefly pause here and note that designing for people with cognitive disabilities in general, and developmental disabilities in particular, is hard. It can be complicated, and it is often neglected. Designing for people with visual and auditory disabilities can be relatively straightforward: ensure that auditory content can be communicated visually, and ensure that visual content can be communicated through audio or braille. That isn't necessarily easy, but it can be straightforward. Sometimes, it can be straightforward to design for people with cognitive disabilities. For example, write in plain language. Or create neat, clean layouts and interfaces. However, there are nuances that require careful and critical thinking (and likely usability testing) to see and to understand when it comes to designing in ways that work for people with limited memory, attention, and problem-solving skills. Designers and developers must ask themselves, what does this website or app cognitively demand from the user? I think answering that question is often neither simple nor straightforward. It's not a simple checklist.

Adaptive strategies and assistive technologies for persons with intellectual and developmental disabilities are also likely to benefit many others, including those learning a foreign language and persons with attention deficit hyperactivity disorder (ADHD).

## Dyslexia/Reading Disabilities

People with dyslexia have trouble reading and processing text.

For people with reading disabilities, it can be helpful to change the font, size, and colors/contrast of text. Text-to-speech (TTS) software can be helpful when reading or writing. Speech-to-text (STT) software alongside spelling and grammar checkers can support writing. Additionally, people with reading disabilities benefit from additional time when reading and writing.

##  Math Disabilities

Math and computational disabilities can cause difficulties learning math and performing calculations (including those involving money). Dyscalculia specifically affects someone's ability to understand arithmetic and perform calculations. Dysgraphia is a writing disability that can often cause challenges for students who are learning math.

People with math disabilities can benefit from using calculators and being given additional time to complete tasks. Graph paper, [manipulatives](https://www.ldatschool.ca/manipulatives-support-math-learning/), and other notation and organizing tools can also help.

## Psychological and Psychiatric Disabilities

Psychological and psychiatric disabilities include anxiety, depression, eating disorders, and schizophrenia. People with these disabilities face social stigma and discrimination, and certain environments may exacerbate their symptoms, although this can vary from person to person.

Some people with psychological or psychiatric disabilities use guided meditations or certain apps to help manage their stress or mood. Carefully preparing and curating their environment can also help support others.

## Multiple/Compound Disabilities

Some people have multiple or compound disabilities. This can be particularly common for people with intellectual or developmental disabilities. I've known people with developmental disabilities who also have vision disabilities, auditory disabilities, seizure disabilities, and/or mobility disabilities.

People with multiple disabilities are more likely to face social stigma and discrimination, in addition to the barriers presented by their individual disabilities.

Additionally, when someone has multiple disabilities, one of their disabilities can interfere with the adaptive strategies that might assist with their other disability. For example, for people who are blind, screen readers can be a great tool for making computers accessible. However, screen readers can be challenging to learn, particularly if the individual also has developmental disabilities. I'm reminded of Marilyn Frye's birdcage analogy --- it's not the one bar that traps the bird, it's the compound set of them.

For people who have multiple disabilities, it is important to use all relevant adaptive strategies, assistive technologies, and inclusive design principles. But for the reasons described above, I think it's also important that we go beyond just that, that we go above and beyond. For example, designers and developers should target <abbr title="Web Content Accessibility Guidelines">WCAG</abbr> level AAA criteria, rather than just level AA. Additionally, while people with all sorts of disabilities can benefit from occupational therapy, for people with multiple disabilities, I think working with a skilled occupational therapist can be especially beneficial. Finally, because it is common for people with developmental disabilities to have compound disabilities, it is extra important to design for people with cognitive disabilities, to present information neatly, in plain language, with supporting images, audio, and video.
