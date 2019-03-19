---
layout: post
title:      "Moving From the Learn IDE to a Local Environment"
date:       2019-03-19 13:58:14 -0400
permalink:  moving_from_the_learn_ide_to_a_local_environment
---


As we move through the course one of the things that become apparent is the need to use a local IDE (integrated development environment) as opposed to the Learn IDE.  The Learn IDE has many things going for it such as the ease of use, the clean and clear interface, speed, and its overall simplicity.  However, it slowly begins to show it's weaknesses such as server issues, lack of customization, and the largest issue becomes clear, as a developer you won't be using Learn.  You will need to use a local IDE in the real world and learn how to select the IDE for the project you're working on, customizing your work environment and configuring your IDE to work best for you and the needs of your company.  

Luckly for us Flatiron School offers us a quick method for us to convert to an integrated development environment.  

If you have Mac OSX your convertion is pretty straight forward.  I won't go into details as the Learn instructions are clear enough and I can't explain them better than they are here: http://help.learn.co/technical-support/local-environment/mac-osx-manual-environment-set-up.  

For Windows users, things are a bit trickier and more often than not, lead to a pretty awkward learning curve.  Before I continue, I want to make things very clear I understand why Flatiron School choose this route for its students.  It introduces it's students to Linux.  For most students here this will be their first introduction to Linux and for first time users, it's difficult to use.  You need to teach your users how to find proprietary drivers for the hardware they are using, teach them how to run certain commands through the terminal, and most importantly teach them the differences between Linux distributions.  For a bootcamp, it will take too much time getting students up and running.  For the reasons above I agree with how Flatiron School approached the issue.  Linux is important for developers and everyone should understand to a certain degree how to use Linux.  For students who wish to grow into stronger developers and branch out into other fields it is almost mandatory to have some proficiency in the OS(s). Now for those who don't have such aspirations, there is a simpler, and more efficient way to do things.  

Windows 10 intoduced the Windows Subsystem for Linux this will allow the user to use Bash without the use of a Virtual Machine.  You will have the ability to use most if not all the commands of the Linux distribution of your choosing.  First thing you need to do it enable the Windows Subsystem for Linux (WSL) through Windows Features options.  I've noticed some writers suggesting to enable Windows Hyper-V as well.  I personally don't have the knowledge to suggest if you should or should'nt.  In my experience it leads to certain applications crashing at load.  This happens when I try to run certain games, and applications.  

At the moment you have access to Ubuntu, openSUSE Leap, SUSE Linux ES (server), Debian, and Kali, all through the Microsoft store.  I choose Ubuntu because I had some experience with it in the past.  You may ask me how did I come to learn about this?  Well, to my surprise the steps needed to get everything up and running was sent to me from another student in my cohort - Sim I'm talking about you buddy, and an even bigger surprise was to look at the author of the article explaining the best way to set up the environment was a former Flatiron Student and current instructor, Micah Shute!  His curiosity and clear explaination of the steps  continues to help students work more efficently since he published his guide last September.   

A link to Micah Shute's article is here: https://dev.to/micahshute/setting-up-windows-subsytem-for-linux-3b7n.  

As I come to the end of this blog I want to remind people that Linux is something that all people should learn to use!  It should be mandatory to learn it, but I understand that it would take too much time for a student in a bootcamp to learn. If you are a current student, future student, or someone who has yet to touch any Linux distribution, please do take some time and learn how to use it.  It will only benefit you as a developer.  
