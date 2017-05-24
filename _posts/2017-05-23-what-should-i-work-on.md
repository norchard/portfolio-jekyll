---
layout: post
title: What Should I Work On?
description: A Mini Guide for New Programmers
---

Last year I was a web designer with a time-consuming programming pastime. In August I left my job to travel and study full-time. This post is about what I learned from nine months of self-study and the resources I used.

### Bootcamps might not be for you
Bootcamps are great for people with financial resources who want to dive into web development without previous technical experience. I opted out of doing a bootcamp for three reasons:
-  They are expensive.
-  I already knew HTML, CSS, and some Javascript. Part of any bootcamp’s curriculum would have been redundant for me.
-  Bootcamps tend to focus on web-dev-specific tools, not computer science fundamentals.

### Self-study is free, but hard
Self-discipline can be an obstacle to self-study, but it’s a straightforward one. You have a list of things you want to accomplish. Maybe you reward yourself for checking items off your list: Do your to-dos; eat some ice cream.

Self-structure is a less straightforward obstacle. How do you decide what to put on your list? Usually, you have high-level goals that you need to break down into manageable to-dos. I want to become a web developer. Should I learn Python? Should I learn Ruby? What is React??

Being an absolute beginner to programming is kind of like looking at the earth from space while planning a journey across it. Blue, green, and brown forms might hint at what’s down there, but they don't give you much insight into navigating the landscape. There are steep mountains and angry oceans (programming is hard!) and knowing where to start and what direction to move in can make the difference between floundering for months and making significant progress (I’ve done both.)

### A few pointers go a long way
This is where help comes in! Ask someone with a lot of programming experience for guidance. I am not that person, but I will pass on advice from much smarter and more experienced people than myself:

1. [Get comfortable using your terminal](https://computers.tutsplus.com/tutorials/navigating-the-terminal-a-gentle-introduction--mac-3855). Start with creating and navigating directories using `pwd`, `mkdir`, `cd`, `ls`. Read the man pages!

2. Pick one language and learn it well. This could be Ruby, Python, Javascript. Some languages lend themselves better to particular applications because of their communities, but all of them use similar logic. Last year I knew how to write Javascript from mimicking tutorials, but I didn’t really understand how it worked. A lot of beginners echo this sentiment. Tutorials feel productive because you end up with a finished product, but they won’t teach you how to program. Find a introductory book for your language and read it cover to cover. Run example programs on your machine. (The first language I learned well was C. I really enjoyed learning C because the language taught me about memory management. If you’re not interested in low level topics, pick Ruby or Python.)

3. Write as much code as you can and don’t stress over finding the perfect project. You can find exercises on sites like [HackerRank](www.hackerrank.com) or [Leetcode](leetcode.com). For starter projects implement games like tic-tac-toe, rock-paper-scissors, or connect four. Online courses are good for having access to problem sets. (Video lectures also serve as a nice break from reading, but you should still read a book!)

4. Forget frameworks. (React is a framework!) I tried to learn Ruby on Rails before having a strong command of Ruby. It was overwhelming and distracting. Instead, write small programs from scratch. For web applications, use a microframework like Sinatra for Ruby or Flask for Python.

5. Read the docs! There is well maintained documentation for the language you are learning or that new library you are using. While it's tempting to start with a blog post or a tutorial (I know documentation sometimes feels like a dry instruction manual), spending a little more time with the docs always pays off.

6. Bugs are a great way to learn. Embrace them and remember that the answer is almost always in the error message. This is something that I re-learn on a weekly basis.

### Find resources you love
Don’t stick with a resource if you are miserable. There are so many resources readily available online. Every programming book I’ve read was delightful in some way. Don’t read a boring book! I’ve waded through a lot of online courses and books. Here’s the stuff that worked for me:

- [Harvard’s CS50 course][1] is an amazing introduction to computer science complete with lectures, problem sets, reading material, and an IDE. It covers topics ranging from search algorithms to web development. David Malan is brilliant in his ability to simplify and gamify complex topics for the computer science beginner. Take advantage and do all the problem sets—this is the most structure you’ll get while studying on your own.

- [Programming in C][2] is a succinct introduction to C and a great accompaniment to CS50. I started out reading C Programming Absolute Beginner’s Guide, but it was too slow for me. Pick what works for you!

- [The Cuckoo’s Egg][3] is a true crime novel about tracking hackers in the 1970’s. Anyone who thinks computing can’t be dramatic needs to read this book. It's a really fun read when you are learning C because the technology is so dated---it’s easy to understand the systems Stoll is working on.

- [The Comet Book][4] is an awesome resource for learning about operating systems and a great technical reference. I skipped around in it while following along with lectures from Berkeley’s Introduction to Operating Systems. I recently came back to the Event Based Concurrency chapter while learning about the difference between Nginx and Apache servers. It is really well written.

- [Why’s Poignant Guide to Ruby][5] is a whimsical illustrated overview of the Ruby language. I picked up some cool tricks for remembering syntax, like that an argument passed to a block slides down a waterslide into the block `{|x| x + 5}`. It’s not a comprehensive introduction, but it’s a lot of fun to read.

- [The Pickaxe Book][6] is a comprehensive introduction to Ruby.

- [Code][7] is possibly my favorite book of all time. It walks through the construction of a computer starting with a single wire and a lightbulb, building circuits using digital logic, and finally reaching the operating system. The thing is: this book reads like a novel. It is not a technical reference. Read the whole thing from start to finish—you won’t regret it!
<!-- - [Nand2Tetris][8] is cool. -->

### Computer friends are the best
Computer friends are nice, quirky, and excellent resources. Talking through code is a great debugging strategy and it's fun to find out you've been pronouncing `chmod` weird. When I started learning I didn't know many programmers, so I joined groups like [Girl Develop It](https://www.girldevelopit.com) and [Women Who Code](https://www.womenwhocode.com/).  
If you're excited about programming and want to make a lot more computer friends, consider applying to [the Recurse Center](https://www.recurse.com/)!

[1]: https://www.edx.org/course/introduction-computer-science-harvardx-cs50x
[2]: https://www.amazon.com/Programming-3rd-Stephen-G-Kochan/dp/0672326663
[3]: https://www.amazon.com/Cuckoos-Egg-Tracking-Computer-Espionage/dp/1416507787
[4]: http://pages.cs.wisc.edu/~remzi/OSTEP/
[5]: http://poignant.guide/
[6]: https://pragprog.com/book/ruby/programming-ruby
[7]: https://www.amazon.com/Code-Language-Computer-Hardware-Software/dp/0735611319
[8]: http://www.nand2tetris.org/
