# FRDCSA Release Strategy Proposal


## Overview

To facilitate rapid public release of FRDCSA and to redefine the project so as to be more open for public collaborative development, [Panoply-Git](https://github.com/aindilis/frdcsa-panoply-git-20200329) would be unterminalized and become the main branch of the public FRDCSA project. Functionality from Andrew’s instance of the FRDCSA system would be transferred into Panoply-Git, or not, at his convenience. The name Panoply should perhaps be changed to just FRDCSA to reflect that it's actually the official FRDCSA system and not a demo.
  

## Purpose

To facilitate rapid public release of FRDCSA and to redefine the project so as to be more open for public collaborative development.

  

## Background

Right now FRDCSA can’t be released because it’s serving as Andrew’s personal configurations and is interspersed with his private data. Panoply-Git is a redacted partial version of Andrew’s FRDCSA system that he released for demonstration purposes but didn’t intend to maintain. The Panoply-Git system has always been considered terminal.

  

Since its release it has diverged from Andrew’s private FRDCSA system as he has continued to develop the latter. Andrew has considered developing scrubber/redactor tools to remove his private data to create a releasable version of FRDCSA that won’t be a terminal demo version like Panoply-Git and won’t have to diverge from his own system. He has estimated 1.16-2 years to finish the necessary tools to produce a “clean” redacted version of FRDCSA for public consumption. Andrew is likely the only one who could write these tools.


## Proposal Details

Instead of taking this approach, this proposal suggests to simply treat Andrew’s version of the FRDCSA system as his own personal configurations & private data, and to instead unterminalize the Panoply-Git system and deem it the main branch of the public FRDCSA project. Functionality from Andrew’s version would be transferred incrementally into Panoply-Git, or not, at Andrew’s convenience. The result would be that the FRDCSA project would (at least partially) be immediately opened up for public consumption and collaborative development.

These two systems are not intended to be two diverging forked branches of the same system but rather logically distinct systems. An analogy could be made that under this proposal, Panoply-Git might be to Andrew's version/instance of FRDCSA as Linux is to a snapshot of Linus Torvalds's personal computer. The idea is to extract the generic reusable components, the means to initialize a new user's fresh environment & provision their machines, etc.. from Andrew's private install.

This isn't intended to be Bob's forked version of Andrew's system it's intended to be the generic reusable core of Andrew's FRDCSA system, extracted from Andrew's private install. Andrew should continue to be in charge of it as it's still just Andrew's FRDCSA system, and ideally also be using it as part of his regular workflow in conjunction with his private configurations that he maintains independently (just as anybody else would maintain their own private configurations independently). If Andrew isn't personally invested in and participating in the development of the reusable public system then the idea of another developer attempting to develop on top of ex.. the current Panoply release becomes much less compelling.

## Notes on divergence

This proposal would produce a divergence between Andrew’s version of FRDCSA and Panoply-Git, but that is intentional, as Andrew’s private personal configurations and the collaboratively developed public FRDCSA project should be two logically separate things that are maintained completely independently of each other.

"The other big problem is say I have a script which outputs all the files on all the drives in the system, and if that's stored in version control, it conflicts, based on which machine. So machine outputted data often conflicts."

Both machines should be operating on the same virtual file system. Different work-stations don't get different instances of the system, they only provide a view into the single virtual file system. The script should live in the virtual file system, the data it operates on should live in the virtual file system, and the data it outputs should live in the virtual file system. The virtual file system is what should be under version control, not the concrete file system of any particular machine.

Compare with, ex.. a Google Drive. You only have 1 Google Drive (per account). It's hosted as files on many different machines. It doesn't really care which machines & neither does the user. The Google Drive isn't a snapshot of a particular machine's hard-drive, it's abstract and independent of specific hardware. When you get on a different workstation you open up the same Google Drive with all your files just exactly as you'd see them from any other workstation. (Disregarding CAP theorem limitations for simplicity). 

Even when machine-specific data is recorded and put under version control, it should be put into version-control disambiguating which machine it refers to. Ex.. if you self-hosted a replica of Google Drive on your own collection of hardware, you might want to run monitoring tools to monitor the status of all your hardware. You might save a representation of your total hardware configuration (a snapshot of *all* the machines, not just for any particular individual machine) into the virtual file system and version-control this. 

To clarify: if you have a snapshot of a system in version control, and you initialize two new instances from that snapshot, and then modify each instance independently, then you have a divergent fork. Ex.. you have a script that will read some machine-specific info & print it to a file called "specific-data" in the machine's file-system, and you run it on each machine and then try to commit a new snapshot of the machine's file-system to version control, you have a conflict on the "specific-data" file.

If on the other hand, you don't initialize two new instances of the system, you rather add two machines into the existing instance, record the change to the instance in version control, such that the config/data specific to each machine is stored in the same repository, then the machines don't produce a conflict. Ex.. you have a script that will read some machine-specific info & print it to a file called "<machine-id>/specific-data" in the virtual file system. You can run it on both machines and commit to version control without conflict.
