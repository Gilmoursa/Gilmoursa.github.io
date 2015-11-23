---
layout: post
title: "More about Git"
modified:
categories: blog
excerpt: "Thoughts from using Git for a few weeks now"
tags: [git]
image:
  feature: bg-3.jpg
date: 2015-09-30T14:44:47+09:00
share: true
---

##Introduction
A few months ago I wrote an article on Git, what it was, how it worked, a little bit of history. If you're interested in learning about Git, I suggest you start there. If you've used Git before and you feel comfortable with the basics, then read on. I'll explain how to setup aliases and work with Github.

##Setting aliases and getting started
Aliases are shortcuts for entering commonly used commands in the terminal. For example if you're often typing `git commit -am` it might be helpful to have an alias of `gcam` to save a bit of time. If you're going to be working in git frequently, which any good developer should, it's handy to have a set of aliases at your disposal. I've included a list below that you can copy into your bash profile.

 - `alias l='ls -lah'`
 - `alias gcl="git clone"`
 - `alias gst="git status"`
 - `alias gl="git pull"`
 - `alias gp="git push"`
 - `alias gd="git diff | mate"`
 - `alias gc="git commit -v"`
 - `alias gca="git commit -v -a"`
 - `alias gb="git branch"`
 - `alias gba="git branch -a"`
 - `alias gcam="git commit -am"`
 - `alias gbb="git branch -b"`

###Where's my bash profile?
You'll find it in your root directory, just type `~` into terminal then `ls -lah` to view all of your files, including the hidden ones (that's what the `h` is for). *If you don't see it, just create one by typing `mkdir .bash_profile`*. Once you find, or create your bash profile, open it by typing `subl .bash_profile` if you have Sublime Text, or typing `open .bash_profile` to open your computer's default program for that file type, it should be TextEdit. Once inside your bash profile you can add the aliases (above) or write your own.

##Typical Git Workflow
Someone sends you a link to a project's repository hosted on Github. 

###Fork it
You'll see an option to fork, or make your own, repository at the top of the screen. It's a small button that looks like the Flux Capacitor from Back to the Future. Once you click this, it will bring you to your own copy of the repo, or repository. From here you should see a URL at the top of the page. It might say HTTPS or SSH. If it says HTTPS change it to SSH. It will save you a small headache later, I'll explain. 

###Save it locally
Next, open your terminal, `command + space` then type `ter` it should autocomplete the rest of *terminal*, hit `return` when you see it autocompleted. Navigate to where you would like your repo to live.

**Remember:**`cd ..` will take you up a directory and tab completion will autocomplete directory names as you type.

Once in your desired location, type `git clone` then copy the URL you saw earlier in Github. *Alternatively, you can use your new alias (above) and type `gcl` then the URL.

###Make some changes
Open your file and make whatever changes you want. When you're finished, add your files to a commit by typing `git add` and the file you changed or `git add .` to add all the changed files. You'll notice that all the git-related commands start with `git`. It's quite nice. 

Next, you'll want to save your commit. This is done by typing `git commit -m` followed by your message in quotes. It's mandatory that you include a message with your commit. Be as specific as possible with your commit message. Ideally you should be able to go back through your history of commits and see everything that went into the creation of the repository. *Instead of `git commit -m` you can use the alias above and type `gcam` then your message.

###I forgot to fork my repo before I cloned it 
No worries. I've done this many times. Just type `git remote -v` to view the current push/pull path to verify that it's not going to the correct place (if it ain't broke don't fix it). If you're sure it's wrong, find the repo on Github and fork it. Now copy the SSH path from your forked repo. Next type `git remote set-url origin` and copy in your SSH path. Now you're all set.

###Making Branches
Ideally you're never working in master. You always create a seperate branch, make some changes, test your code, then merge into master. You can do this by navigating to your local repo, that is the copy of your files that live on your system. Then type `git co -b` and give your new branch a descriptive name. `git` is just the prefix for all git commands, `co` is checkout, and `-b` is your branch. The nice thing about this command is it will create a new branch and automatically switch you over to it. 

When you're finished with your changes, and you tested your code, merge it back into your master branch. First commit your changes `gcam` followed by your message, then `git co master`, and finally, `git merge` branch name you just worked on.

