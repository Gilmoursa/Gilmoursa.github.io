---
layout: post
title: "Package Control"
modified:
categories: blog
excerpt: "What's this package control everyone's going on about?"
tags: [pre-work, bash]
image:
  feature: bg-3.jpg
date: 2015-10-05T08:00:00-04:00
share: true
---

<iframe src="//giphy.com/embed/HhocXRaJRi7QI" width="50%"></iframe>

##What is this Package Control everyone's going on about?
*Packages*, are custom plugins, snippets, and macros. *Package Control* is the [Sublime Text](https://www.sublimetext.com/) package manager. It includes 2,500 packages that do everything from expand HTML tags to highlight hexadecimal colors to autocomplete file names. Additionally, users can add [BitBucket](https://bitbucket.org/) or [GitHub](http://www.github.com) repositories themselves. The stats on package control are incredibly impressive.

>Today this server delivers around 5TB of compressed json data a month and has seen over 2.7 million unique clients connect. [Full stats here](https://packagecontrol.io/stats).

<iframe src="//giphy.com/embed/fdOA43sHFE6Pu" width="80%"></iframe>

##Alright, I'm sold. How do I get it?
[Detailed instructions](https://packagecontrol.io/installation) for installing Package Control can be found on the Package Control website. However, the gist is this.

###Simple Package Control Installation
Go to the Sublime Text console via `ctrl+` or `View > Show Console`. A window will open at the bottom of your current Sublime Text window. From there type or copy and paste:

####SUBLIME TEXT 3
```import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)```

####SUBLIME TEXT 2
```import urllib2,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation')```

###What does the installation do?
The Package Control Installation will create the Packages folder, for you. This is the folder where all of your nifty packages will live. This folder is inside your Sublime Text directory in your Applications folder. The installation also downloads the `Package Control.sublime-package` into your swanky new folder.

<figure>
	<img src="/images/packagecontrol.jpg">
</figure>

###How do I get to Package Control?
`cmd+shift+p` will do it for you in OS X or `ctrl+shift+p` in Linux/Windows. This opens the Command Palette which offers you a text field where you can control Package Control. 

####How do I install packages?
- To install packages type `install package` and a window will pop up showing you packages available for install. **Beware:** This is an exhaustively comprehensive list. You'll be best off using the search field to find what you want.

####How do I add additional repositories?
- To add a package hosted on **GitHub**, enter the URL in the form `https://github.com/username/repo`. Don’t include `.git`! **BitBucket** repositories should use the format `https://bitbucket.org/username/` repository.

####How do I remove packages?
- To remove a package type `remove package`. This will delete the package folder and the package name from the `installed_packages` list in `Packages/User/Package Control.sublime-settings`.

**Fun Fact**
You can copy the `installed_packages` list into the `Packages/User/` folder on another computer and Package Control will automatically install the packages for you.

###Alright, I get Package Control, but where do I find the best packages for Sublime Text?
I'm glad you asked. I've compiled a list of several resources for Package Control Packages.

- The [Package Control Homepage](https://packagecontrol.io/) displays *Trending, New,* and *Popular* packages right on the main page.
- The [Google Developers Page](https://developers.google.com/web/shows/ttt/series-1/sublime-text-plugins?hl=en) has an article on useful Sublime Text packages.
- [Buffer Wall](https://bufferwall.com/blogs/2015-04-03-the-best-sublime-text-3-extensions/) has an awesome list of great packages as well.

###A few packages I recommend
- [Auto File Name](https://packagecontrol.io/packages/AutoFileName) are you tired of images not loading or programs unable to locate files? Auto File Name will offer a dropdown menu of file names as you type. It even lets you drill down through several directories like `images/team/accounting/image.jpg`
- [Bracket Highlighter](https://packagecontrol.io/packages/BracketHighlighter) takes the guesswork out of which bracket your actually closing. This is great when you have a million `<div>` tags in HTML or 3 nested iterators in a ruby hash. The package will display the opening and closing bracket on the left hand side for any piece of code the cursor is on.
brackethighlighter

<figure>
	<img src="/images/brackethighlighter.png">
</figure>

- [Emmet](https://packagecontrol.io/packages/Emmet) is one of the most popular packages for Sublime Text with over 1.3 million downloads. It allows you to write HTML in shorthand and expand it using the `tab` key. For example `ul>li*3` becomes 

```<ul>
	<li></li>
	<li></li>
	<li></li>
</ul>```





