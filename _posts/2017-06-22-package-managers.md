---
layout: post
title: Package Managers
description: The Logic Behind the Magic of Install
---

If you want to draw for the first time, someone might hand you a piece of paper and a pencil. They won't spend time discussing where the paper and pencil came from. Instead, they'll tell you about line, form, and negative space. If you want to write a Python program for the first time, someone might run the following commands on your machine:
```
$ apt install python3
$ pip3 install ipython
```
Then they would open iPython and show you some basic Python syntax.

Package management is often glossed over because programming is the writing of programs, not the installing of programs. However, programming is also the organization of programs... and it actually *is* the installing of programs, sometimes. After spending over a year installing and uninstalling (but mostly installing) packages using brew, gem, and npm on my mac, I finally learned how package managers work on a virtual machine running Ubuntu. Understanding how package management works was a pretty satisfying 'aha!' moment for me, so I hope it is for you too.

### What is a Package Manager?
> A *package manager* keeps track of what software is installed on your computer, and allows  you to easily install new software, upgrade software to newer versions, or remove software that you previously installed. As the name suggests, package managers deal with *packages*: collections of files that are bundled together and can be installed and removed as a group.
– [Aptitude User Manual](http://aptitude.alioth.debian.org/doc/en/pr01s02.html)

There are essentially two types of package managers:
- **System-level package managers** are highly integrated into the operating system.
    Ubuntu is a flavor of the Debian Linux distribution, which means it uses `dpkg`, the Debian package manager. `dpkg` is a low level tool that is used to install, remove, and provide information about individual .deb packages. Some packages depend on other packages, but `dpkg` doesn't manage dependencies. User friendly frontend tools like `apt` manage package dependencies and versioning decisions. Both `dpkg` and `apt` come pre-installed with Ubuntu. `aptitude` is another frontend to `dpkg` based on `apt`, with some additional functionality. You can install `aptitude` by running `apt install aptitude`.
- **Language-specific package managers** manage one programming language's libraries and are operating system independent.
    RubyGems is a package manager for the Ruby programming language. It manages installation, dependencies, and versioning of Ruby packages, called gems. [Ruby gems](http://guides.rubygems.org/what-is-a-gem/) include code, documentation, and a gemspec file.

### Search
When I needed to install Ruby to run a script on my VM, I used `aptitude` to search for a Ruby package.
```
$ aptitude search ruby
```
My search returned a long list of .deb packages containing the word 'ruby'. Where did this list come from? A file called `/etc/apt/sources.list` shows the source endpoint for both `deb` packages, which are binary files, and `deb-src` packages, which are source files.
```small
deb http://mirrors.digitalocean.com/ubuntu/ xenial main restricted
deb-src http://mirrors.digitalocean.com/ubuntu/ xenial main restricted
```
My VM is a DigitalOcean Droplet, so the source url is an Ubuntu mirror hosted by DigitalOcean. A mirror is just a duplicate of a canonical package archive. Ubuntu keeps [a list of registered mirrors](https://launchpad.net/ubuntu/+archivemirrors) that are open to use by the general public. DigitalOcean's mirror isn't on that list because it is only intended to be used by DigitalOcean Droplets. Anyone can [create a mirror](https://help.ubuntu.com/community/Rsyncmirror).

### Installation
In order to install the latest version of Ruby (2.3) I could run either of two commands:
```
$ aptitude install ruby2.3
$ aptitude install ruby
```
I chose to run the second because it installs the default version of Ruby, which is currently 2.3, but could change in the future. Upon running the install command I received this prompt:
```small
root@ubuntu:~# aptitude install ruby
The following NEW packages will be installed:
  fonts-lato{a} javascript-common{a} libjs-jquery{a} libruby2.3{a}
  rake{a} ruby ruby-did-you-mean{a} ruby-minitest{a}
  ruby-net-telnet{a} ruby-power-assert{a} ruby-test-unit{a}
  ruby2.3{a} rubygems-integration{a} unzip{a} zip{a}
0 packages upgraded, 15 newly installed, 0 to remove and 22 not upgraded. Need to get 0 B/6,359 kB of archives. After unpacking 28.6 MB will be used.
Do you want to continue? [Y/n/?]
```
Those are Ruby's dependencies! Some of them seem like nonsense. I'm not sure why Ruby needs Lato, but others are logical, like the Ruby library and Rake, which is Ruby's build automation tool (think Ruby Make).

### Organization
Once the install completes, the Ruby binary file is located in `/usr/bin`. If you run `echo $PATH` you can see the search path that is traversed when you run a program from the command line. Mine is the default for Ubuntu:
```
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```
- `/bin` contains binary programs that are necessary for basic functionality, like booting and repairing the system.
- `/usr/bin` is where distribution managed packages are installed -- so anything you would install with `aptitude install`.
- `/usr/local/bin` is where user-installed packages go, including packages installed by language-specific package managers.

`sbin` is where packages that need to be run as root are installed. Now my VM can run `ruby my_script.rb` because it will find an executable Ruby program in `/usr/bin`.

### Gems
Actually, my VM couldn't run my script just yet because I also needed a Ruby gem called `dotenv` to load environment variables into my script. I found it using `gem search` and installed it with `gem install dotenv`.

Where do gems come from and where are they installed? You can find out by running `gem environment`. Among other environment variables, you'll see:
```
- INSTALLATION DIRECTORY: /var/lib/gems/2.3.0
- EXECUTABLE DIRECTORY: /usr/local/bin
- REMOTE SOURCES:
   - https://rubygems.org/
```
The gem source address is `https://rubygems.org/`, but you can add other sources, or [create a local mirror](https://github.com/rubygems/rubygems-mirror). RubyGems is a language-specific package manager, so executable files are installed at `/usr/local/bin`. After installing the dotenv gem, I have a `dotenv` executable file in `/usr/local/bin`. The gem itself is installed in `/var/lib/gems/[ruby-version-number]`. Now I can use the gem by requiring it in my script or I can run the executable at the command-line.

### Help
Most package managers have pretty similar command-line interfaces, including `search`, `install`, `uninstall`. However, some have slightly different commands and functionality, so it always *helps* to run `-h` or `-help` to get familiar with your package manager's UI.

### Super Cow Powers
When you run `aptitude -h` the output will also tell you, following a list of valid usage, actions, and options, that aptitude "does not have Super Cow Powers".
```small
Actions:
install   - Install/upgrade packages.
remove    - Remove packages.
...
Options:
 -v         Display extra information. (may be supplied multiple times).
...
This aptitude does not have Super Cow Powers.
```
`apt` *does* have super cow powers:

```
root@ubuntu:~# apt moo
                 (__)
                 (oo)
           /------\/
          / |    ||
         *  /\---/\
            ~~   ~~
..."Have you mooed today?"...
```
Although `aptitude` doesn't have super cow powers, if you persist you might be rewarded with a drawing.
