= Overview

The FRDCSA (https://frdcsa.org) has been under development for 20
years as of writing ([2020-03-29,02:53:26]).  It is a comprehensive
free/libre artificial intelligence system.  Mainly it collects other
A.I. systems and gets them all to talk to each other.  However, it has
quite a lot of original code as well, maybe over 2 million lines of
code.  The most important individual project is the Free Life Planner
(https://github.com/aindilis/free-life-planner).

= Howto

First, ensure you have Virtualbox 6.1 installed.  For Debian 11
(Bullseye), there is a tutorial here:

https://linuxiac.com/how-to-install-virtualbox-on-debian-11-bullseye/

Next, clone this repository:

`git clone https://github.com/aindilis/frdcsa-panoply-git-20200329`

and change directory into it:

`cd frdcsa-panoply-git-20200329`

Be sure you have at least 10144 MB of RAM free for use with VMs
(otherwise edit the amount of ram in the Vagrantfile - note system
will probably not be able ot run OpenCyc along with FLP if you reduce
the RAM).  Also make sure you have probably at least 48 GB disk space 
free (although machine is about 16 GB decompressed).

Then ensure you have recent versions of VirtualBox and vagrant
installed, and then, in this directory run:

`vagrant up --provider=virtualbox`

The username is andrewdo and the password is temptemp

See the following for more information on how to use it:

https://frdcsa.org/~andrewdo/writings/README.html

= Questions

Please contact me with any questions.  Thank you and enjoy!
