Introduction
====

This repository is a cross-project collaboration space for censorship circumvention tools.
Our initial focus is expanding Tor's [pluggable transports](https://gitweb.torproject.org/torspec.git/blob/HEAD:/pt-spec.txt) work to easily
work in a wider variety of circumvention tools. Initial collaborators include [Lantern](http://getlantern.org),
[Psiphon](https://s3.amazonaws.com/0ubz-2q11-gi9y/en.html), [Tor](https://www.torproject.org/) and 
[uProxy](https://www.google.com/ideas/projects/uproxy/).

Collaboration
====

There are two main collaboration spaces:

**Mailing List**: [Our Google Group](https://groups.google.com/forum/?hl=en#!forum/traffic-obf)

**IRC Meeting**: The Pluggable Transports community conducts biweekly IRC meetings. You can 
find us in #tor-dev at the OFTC network [every second friday](https://www.google.com/calendar/embed?src=dt92shou5q1ooe1kptubhclo4s%40group.calendar.google.com) at 
[16:00 UTC](http://www.timeanddate.com/worldclock/fixedtime.html?hour=16&min=00&sec=0p1=0).

Goals
====

We hope to get to refactor Tor's Pluggable Transport specification in to a core specification that
can be used by a variety of circumvention tools. Each tool can then write up their own project-specific
specification for how to make a pluggable transport work with its internal infrastructure.

What is a Pluggable Transport?
====

Pluggable Transports were defined by Tor, but some (FTEProxy, Meek) have already been adapted to 
other tools (Lantern, Psiphon. They are:

* Standalone processes that accept traffic from a client and route it to a server

* Require client and server-side processes that know how to talk to each other

* Are aimed at obfuscating traffic so that censors can't tell it's coming from a circumvention tool. 


The obfuscation is the hard part, and as long as it's built using fairly generic interfaces (the way that fteproxy is), it can be reused quite easily across projects, even though their mechanisms for managing and communicating with pluggable transports are different.

Current Pluggable Transport integrations
====

| Transports                                           | Support in
-------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| [obfs2](https://gitweb.torproject.org/pluggable-transports/obfsproxy.git/blob/HEAD:/doc/obfs2/obfs2-protocol-spec.txt)         | [Tor](https://www.torproject.org/)                                                        |
| [obfs3](https://gitweb.torproject.org/pluggable-transports/obfsproxy.git/blob/HEAD:/doc/obfs3/obfs3-protocol-spec.txt)         | [Tor](https://www.torproject.org/), [Lantern](http://getlantern.org)                      |
| [FTE](https://fteproxy.org/)                                                                                                   | [Tor](https://www.torproject.org/)                                                        |
| [scramblesuit](http://www.cs.kau.se/philwint/scramblesuit/)                                                                    | [Tor](https://www.torproject.org/)                                                        |
| [obfuscatedssh](https://github.com/brl/obfuscated-openssh/blob/master/README.obfuscation)                                      | [Psiphon](https://psiphon.ca/)                                                            |
| [meek](https://trac.torproject.org/projects/tor/wiki/doc/meek)                                                                 | [Tor](https://www.torproject.org/),  [Psiphon](https://psiphon.ca/)                       |
| [flashproxy](https://crypto.stanford.edu/flashproxy/)                                                                          | [Tor](https://www.torproject.org/)                                                        |
| [socks-rtc](https://github.com/uProxy/socks-rtc)                                                                               | [uProxy](https://www.google.com/ideas/projects/uproxy/)                                   |
| [flashlight](https://github.com/getlantern/flashlight)                                                                         | [Lantern](https://www.getlantern.org/)                                                    |


Tor's Pluggable Transports links:
=====

[pt-spec.txt](https://gitweb.torproject.org/torspec.git/blob/HEAD:/pt-spec.txt)

[Extended ORPort](https://gitweb.torproject.org/torspec.git/blob/HEAD:/proposals/196-transport-control-ports.txt)


[Extended ORPort authentication](https://gitweb.torproject.org/torspec.git/blob/HEAD:/proposals/217-ext-orport-auth.txt)

Also:
https://www.torproject.org/docs/pluggable-transports
https://trac.torproject.org/projects/tor/wiki/doc/PluggableTransports

