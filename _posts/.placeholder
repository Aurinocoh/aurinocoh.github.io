---
layout: post
title: Why I Chose NixOS
tags:
  - nixos
  - declarative
---

# Why I Chose NixOS

When assembling a homelab there's a great many choices of operating systems to use as a foundation. [Proxmox VE](https://www.proxmox.com/en/proxmox-ve) is an option that rises to the surface and I find it difficult to oppose those who choose it.  [Debian](https://www.debian.org/) has been a staple in the Linux world for about 25 years (circa 2000).  Choosing such a venerable distribution to base a homelab on gives raw control and is another wise choice that I would be hard-pressed to oppose.  [NixOS](https://nixos.org/) is a different alternative.  Part of a family of operating systems which focus on being declarative.  Other options exist, some of which may even be better choices for the most restricted view of how I am utilizing NixOS.  That said, even if I am not using them yet, NixOS offers me declarative control all the way down to my kernel and its modules.

## What's The Point of Declarative

I appreciate that many feel that not being able to simply ssh into a machine run a command and have new software running easily makes a system less usable.  Under ideal conditions the process isn't particularly different for NixOS.  A simple change to add the package you want to the list, followed by a ``nixos-rebuild switch`` will quickly install a package.  Adding a single line to a list shouldn't be too difficult for most, but why bother?  The reality of usability here is that it works both ways, cleanly, every time.  If you remove a package from that list, NixOS doesn't uninstall that package, it _builds a whole new system state that never included it_.  This solves the eternal problem of messy uninstalls and may well be worth using NixOS for without any other gains.  The ever-eroding state of a long-running machine is a significant problem. When you get right down to it, a proper software upgrade is little more than an uninstall of an old version and install of a new version.  Consider that even a most minimal system doing useful work is likely to have 1,000 packages and that many of those are on a staggered, three month average update cycle and you can end up conservatively doing 2,000 updates in a year.  When you realize that each of these is fundamentally a uninstall and reinstall process if being done properly, that's a lot of files that can be left dangling, interfering or increase your attack surface.  NixOS solves this, among other things by intelligently and rapidly building a completely new _generation_ or state of your system.  This isn't a long process for many cases as the majority of cases as the files required to do so are often already cached. This cacheing can be on your machine, but optionally on a remote cache, either the public NixOS one, or a private one. Running your own cache with tools like [Attic](https://attic.sh/) allows you to maintain your own build server, build processes and cacheing. Running Attic like this isn't trivial, however, it does give you ultimate control and auditability.

It's also worth noting that your entire configuration is stored as text files.  Text files can be stored in git.  Text files stored in git can be easily cloned down and used to turn a given system into a copy of the one from that repository.  Be this a restore from backup or a new machine.

## Reality Clashes with My Use Case

Bluntly: I am using NixOS like it's [Flatcar](https://www.flatcar-linux.org/) in a lot of ways. I use NixOS as a container host that I can control declaratively.  In many ways I don't reap the benefits.  This usage pattern grew out of two concerns:
* NixOS when you deviate from the expected use can be nightmarishly complex to fix.
* Containers (and to a lesser extent, VMs) offer an isolation profile that I find useful.

The first portion is the result of spending entirely too long fussing with NixOS' configuration files trying to make weirdly specific things work in a large and complicated context.  I've learned over a great many years that your _working window_ increases with your skill, understanding and the amount of heuristics and encoded, reflexive knowledge.  This working window will almost always be dwarfed by overly large contexts and ever increasing complexity.  As the amount you're required to keep in your mind to work on something grows, you must decrease the mental complexity of holding that context in your head, through direct simplification, sure, but also through structuring the information in a way that is intelligeble.  Segmenting things into containers allows attacking that context size directly by seeking to solve one thing at a time, and using NixOS in those containers means attacking the complexity by working towards a common structure.  This also resolves the other contention.

## NixOS Into My Future

NixOS is likely to stay into my future, it solves real problems.  It gives me the amount of control I desire.  It makes sense for my use case, and for future use cases I have in mind.  While I've avoided diving deeply into the technical details, hopefully I've made the case for a declarative operating system.
