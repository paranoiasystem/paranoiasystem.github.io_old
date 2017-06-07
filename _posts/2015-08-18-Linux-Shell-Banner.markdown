---
layout: post
title:  "Linux shell banner - [How To]"
date:   2015-08-18 09:53:54
categories: [how-to, linux, shell]
---
Hi, today I show you how to make a shell banner for your linux distro.

The shell banner we go to create are like this 

<img alt="shell banner 1" src="/assets/img/shell-banner-1.jpg" width="60%" />

or this 

<img alt="shell banner 1" src="/assets/img/shell-banner-2.jpg" width="60%" />

For make a shell banner like first type. Follow this step:

1.	Go on this [site](http://patorjk.com/software/taag/#p=display&h=3&v=3&f=Big%20Money-ne&t=ParanoiaSystem), here you can simply create your ASCII art from a word.
2.	Now, copy and paste the ASCII art in a file based in your home directory, call the file _".banner"_.
3.	Now using your favorite editor edit the file _".bashrc"_ and add at bottom of file this line _"cat .banner"_.

If you want a shell banner like the second type  Follow this:

1.	Install git on your linux system if you don't have this package.
2.	Download the latest source at https://github.com/KittyKatt/screenFetch
3.	In a terminal, make the file executable by doing the following: `chmod +x /path/to/screenfetch/screenfetch-dev`
4.	Then, either keep it there, or move it to somewhere in your $PATH to make it available without having to use the full path to the script
5.	Now using your favorite editor edit the file _".bashrc"_ and add at bottom of file this line _"screenfetch-dev"_.

I hope you enjoyed this post. I will continue to do this type of posts.
