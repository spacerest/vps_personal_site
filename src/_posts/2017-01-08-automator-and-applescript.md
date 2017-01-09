---
layout: post
title: "automator and applescript"
date: 2017-01-08 00:00:00 -0600
comments: true
categories:
---

This week I set up some macros on my computer to automate some useful tasks: 
- saving screenshots to weekly directories with customizable names
- saving selected text and the associated URL from Chrome directly in these markdown files to keep track of what I'm doing and learning

My personal computer is a mac laptop running Sierra 10.12.2, so to do this I am using Applescript via Automator. This was my first time using either of these and I'm looking forward to learning more in the future.

The reason for wanting to write these macros is because I feel like I've been learning a lot lately without having the foresight / hindsight to log it here, and these two shortcuts will push me along. As long as I've found at least one thing I want to screenshot or one string of text I want to save, I'll automatically have the makings of a post started for myself.

╚╚\|░▄░\|╝╝
{: class="center robot" }

1. [Keyboard Shortcuts and Automator](#one)

2. [Applescript](#two)

3. [Conclusion and Sources](#three)

╚╚\|░▄░\|╝╝
{: class="center robot" }

{: id="one" class="section_header"}
Keyboard Shortcuts and Automator
===========

Automator is straightforward. To get to know it I followed a basic walkthrough by David Sparks [here](https://www.macsparky.com/blog/2008/3/2/automator-walkthrough-auto-save-and-load-wallpaper.html) wherein you can point Automator to Safari and save whatever image is open in your front browser window and set it as your wallpaper. 

My main goal with Automator in this case was to run some Applescript (discussed later) with a keyboard shortcut. As far as I know, a user's route to set keyboard shortcuts on macs is by making Services, and we can make Services with Automator. There might be other ways, but this is the way that I found

{: .center }
![set_keyboard_shortcut]({{ "/assets/images/2017-01-08/set_keyboard_shortcut.png" | prepend: site.baseurl }})

In the image below, you see the Applescript as the only action for the Service saved as "chrome_selection_to_blog." In the upper right hand corner of the screenshot you can see a gear turning -- this indicates that a Service was running (one of the two I'm talking about here) when I was taking the screenshot. (Apologies if these images are small in this post -- feel free to open in a new tab to see it larger).

{: .center }
![automator_sample_screenshot]({{ "/assets/images/2017-01-08/automator_sample_screenshot.png" | prepend: site.baseurl }})

{: id="two" class="section_header"}
Applescript
===========

To download the scripts themselves, go over to my [scripts_for_automator repo](https://github.com/spacerest/scripts_for_automator). 

The majority of what I learned in setting this up was about Applescript syntax. There are quite a few sources listed at the bottom of this post which highlight what I was searching to learn how to do. My favorite of my sources is [this post about Applescript and dates](http://macscripter.net/viewtopic.php?id=24737) by Nigel Garvey, Kai Edwards and Adam Bell, which has comprehensive details about how to interact with dates and times 
> with a little mathematical forethought and the exploitation of some of the peculiarities of date variables and AppleScript[.]
I needed this because of the weekly cycle I'm shooting for for these posts, so I need my scripts to check what day of the week it is and when the next Sunday is going to be to know where to save the content.

Something that challenges me, for whatever reason, is how AppleScript interacts with folders and files. I imagine this has something to do with the "everything is an object" theme I see in some languages, but it might be another aspect of it that confuses me. Anyway, a shortcut I took around this was by using lots of <code>do shell script</code> blocks so that I could interact with files and folders how I normally do from the command line. I hear that this has a negative impact on runtime, but I could be wrong.

{: id="three" class="section_header"}
Conclusion and Sources
===========

##Conclusion

I'm happy that this is working so far. All the URLs and screenshots on this post were automatically included via these macros. I want to make a slight variation to the screenshot script so that I can do the same thing with gifs.

##Sources

- [Smile 3.8.0 (build 959) full edition](http://www.satimage.fr/software/en/downloads/index.html)

- [An AppleScript dialog textfield example](http://alvinalexander.com/blog/post/mac-os-x/applescript-add-textfield-dialog)

- [Automate taking a screenshot of specified area](http://apple.stackexchange.com/questions/113416/automate-taking-a-screenshot-of-specified-area)

- [DateOfThisInstanceOfThisWeekdayBeforeOrAfterThisDate](http://macscripter.net/viewtopic.php?id=24737)

- [How to add words to a text file using just open terminal command (no editors) and then save the text file](http://askubuntu.com/questions/435291/how-to-add-words-to-a-text-file-using-just-open-terminal-command-no-editors-an)

- [An AppleScript list size example](http://alvinalexander.com/apple/applescript-list-size-example-count-number)

- [AppleScript: How to split a string](http://erikslab.com/2007/08/31/applescript-how-to-split-a-string/)

- [tell application "System Events"   keystroke "c" using command down end tell set theText to the clipboard](http://macscripter.net/viewtopic.php?id=33575)

- [Vimium](https://vimium.github.io/)

- [16 0x10 ANSI_Y](http://apple.stackexchange.com/questions/36943/how-do-i-automate-a-key-press-in-applescript)

- [Complete list of AppleScript key codes](http://eastmanreference.com/complete-list-of-applescript-key-codes/)

- [Is there an easy way to clear/empty the clipboard?](http://apple.stackexchange.com/questions/55146/is-there-an-easy-way-to-clear-empty-the-clipboard)

- [AUTOMATOR WALKTHROUGH - AUTO SAVE AND LOAD WALLPAPER](https://www.macsparky.com/blog/2008/3/2/automator-walkthrough-auto-save-and-load-wallpaper.html)

- [Referencing Files and Folders in Applescript](https://developer.apple.com/library/content/documentation/LanguagesUtilities/Conceptual/MacAutomationScriptingGuide/ReferenceFilesandFolders.html)

- [Rename only if needed in Applescript](https://forum.keyboardmaestro.com/t/rename-only-if-needed/1342)

- [Regular Expression or Wildcards in Applescript](http://macscripter.net/viewtopic.php?id=34467)

