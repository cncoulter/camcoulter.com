---
SPDX-FileCopyrightText: 2023 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "How I Take Notes (Digitially)"
published: true
date: 2023-12-30 13:17
categories:
- Web Design
tags:
- HTML
- CSS
- Bash
- Pandoc
- GitHub
- notes
description: "Most of my digital notes live together in one system, a folder with Markdown files that I can compile together into a simple website."
image: desk-keyboard-notebook
toc: true
---

Lately I have been rediscovering the joy of handwritten text. I spend so much time on a computer for my job, it is a relief to be away from a screen. I feel more relaxed handwriting with a pen and paper, and my mind can shift into a different pattern of attention. I hear it helps with memory and recall too.

This post is not about that. There is a place for handwritten notes, and there is a place for digital notes. Digitally, I have notes about my to-dos, goals, and priorities, about my favorite recipes, about various command-line utilities, about games I get invested in, and more. I also have a lot of lists. I like to make lists. You should see my reading list. It is joyously, stupidly long.

Admittedly, I have digital notes scattered in a few different places, but most of them live together in one system, a folder with Markdown files that I can compile together into interlinked HTML files. Let me explain how that works and why I like it. I'm sharing because I think it is an awesome system with some real advantages and because it's different than what most people use or consider using. If you think it's cool, I have made a GitHub repository that you can clone and use to try it out yourself.

## How It Works

I have a folder for my notes. That folder has folders within it for different categories, such as to-dos, food, games, and reference. Each note is a plain text file written in Markdown. I have a Bash script that uses Pandoc to convert the Markdown files into interlinked HTML files. In effect, it is a very simple website. 

I have a homepage note that links to my most used notes and to an index note for each category, which in turn links to all the notes in that category. I actually have the homepage note set as my homepage in Firefox so that it's easy for me to view my notes. If any two notes are related to each other, they may also link to each other. I use a classless CSS stylesheet to add some basic styling to the rendered HTML files. I use Git to version control it all, usually committing a snapshot every month or so. I sync my notes folder with Nextcloud to back it up and make it available on my phone.



## Advantages

There are a lot of advantages to this system of taking digital notes.

It's accessible. Plain text files and simple web pages work well with assistive technologies like screen readers, and it is easy to change the size, font, and color of text to make it more readable. I can see okay, but I do sometimes get eye strain when I spending too much time on screens. When this happens, I love being able to use my browser's zoom to make my notes just a little bit bigger.

It's adaptable and platform-agnostic. You can use whichever text editor and browser you prefer. Sometimes I will edit my notes using different text editors depending on the day, my preferences, and what exactly I'm writing down or updating. You can also use whichever cloud/syncing service you prefer or are already using, or not sync your notes at all if you don't want to.

It's future-proof. I am confident I can keep using this notes system for decades. Plain text files and web browsers have already been around for decades, and I'm sure they will be around for decades longer. Markdown is simple, and if for some reason I have to stop using Pandoc to compile my notes, I am confident I can find another command-line utility to do so, and even if for some reason I can't, my notes still exist as readable and future-proof text files. I won't need to migrate my notes if I switch to a different operating system or if a provider goes out of business.

It's free. It's not a paid service.

It's private. You don't have to sync your notes at all; you can keep them all on your personal desktop computer if you'd like. If you want to sync your notes, you can use whichever service you are comfortable with: Google Drive, iCloud, Dropbox, your own personal Nextcloud server, or something else. You can even sync your notes directly between your personal devices without any intermediaries using a tool like Syncthing, and you can backup your notes using whatever backup system you are already using.

It has simple, easy, and robust version control through Git. If I accidentally delete a file, I can go back and recover it. I can feel free to delete old things, knowing that they are out of the way yet still recoverable if I later change my mind. I can even revert my entire notes folder to what it looked like in an earlier year if I am feeling nostalgic or curious about my past, and then restore it to the present. And if you aren't interested in version control, the system still works fine without it.

You can use Git to share and collaborate on a repository of notes with others.

It's flexible. Your notes can be structured in a top-down, linear fashion, but they can also be linked together in ways as nonlinear as Wikipedia. I stick to using plain text files, but you could absolutely include images or PDF files within this system as well if you want. If Markdown is not sufficient for your needs, you can include HTML code directly within your plain text Markdown files. For example, you can include an accordion component within your rendered website by adding a [<code>&lt;summary&gt;</code> element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary) within your Markdown notes. And Pandoc actually supports an [extended Markdown syntax](https://pandoc.org/MANUAL.html#pandocs-markdown), one that makes it easy to include [footnotes](https://pandoc.org/MANUAL.html#footnotes) for example.

It's searchable. If I want to search across all of my notes for something, I can use an editor like Visual Studio Code that lets you search all files within a folder at once. I can even add tags to notes if I want. All I need to do is add "@cats" somewhere in the note, and then I can search my notes folder for any notes that include "@cats". True, the tagged notes would not necessarily be all linked together, but if I wanted to take the time to link them together, I still could.

It's lightweight. My notes folder weighs in at a total of 9 MB. The bulk of that (7.8 MB) is my journals, going back 9 years, before I even started this notes system. (Did I mention that it can be easy to import new content into the system? You just need Markdown files, and you can even use Pandoc to convert Word files to Markdown.) Text editors, browsers, and Pandoc take up more space on my system, but those are programs I would already have installed anyway.

## Drawbacks

There are some drawbacks I can think of.

It requires technical know-how. You do not need to be a programmer or a web designer to use this notes system, but you should have basic computer skills, and you should be ready to learn the basics of Markdown and Git if they are new to you.

It requires some setup. It took me a while to set this up, but if you copy the folder I share below, the setup time is pretty quick: just get familiar with the system and start filling in and linking your notes. That said, it will take more setup time than just opening the notes app on your phone.

It is moderately complex. If I want a new note to be reachable through the rendered website, I need to add a link to it to the relevant index page. It doesn't take a lot of time to do that, but it is a degree of overhead that other notes systems lack. I do also need to routinely manually execute the Bash script to update the rendered website, so that the HTML output mirrors the Markdown input. (That said, you could use the Chron utility to routinely build your notes without you needing to manually do so.)

It assumes you have a desktop computer, and you may not be able to compile your Markdown notes into HTML files on mobile phones and tablets. I think this point is moreso a drawback of today's mobile operating systems, which in theory should allow you to use simple command-line utilities like Pandoc and Git but which in practice obfuscate or prevent you from doing so. That said, you should still be able to sync these notes to your mobile devices, view and edit the plain text Markdown files, and view the already-complied HTML pages.

## Try It Out

I set up a [GitHub repository](https://github.com/cncoulter/notes-to-website) that you can copy to set up your own notes system as I described here. Be sure to read the included ReadMe page for detailed instructions on getting set up and using the system.

If you download the GitHub repository to your desktop, you can open the included index.html file to preview this notes system in your browser to get a better idea of it, but I also included an example of what it might look like here on this site in case you just want to see it in action:

<a href="{{ site.baseurl }}/notes-to-website/" class="link-turncoat link-turncoat--standalone">View notes-to-website example site</a>

***

What do you think about this method of taking digital notes? Are you interested in trying it out or have any use cases for it yourself? And please let me know if you start using it yourself — I would be eager to hear about others' experiences with it.
