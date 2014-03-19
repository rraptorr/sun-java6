Please note that Java 6 reached its end of public updates and Oracle
will not release any more updates (latest being 6u45). For details
please see http://www.oracle.com/technetwork/java/eol-135779.html

Introduction
------------

Due to licensing problems Java 6 was recently removed from Debian
testing and Debian stable/oldstable was stuck with Java 6u26. Given
security updates in later Java versions, this leaves no choice, but
manual Java update (OpenJDK not being an alternative for many).

I didn't like the idea of installing Java by hand on my Debian
systems, so I've looked for updated Java packages. As I was unable to
find ones, I've decided to make my own, so I've pulled latest package
sources from the Debian Subversion repository and adapted it to the
latest Java 6.

Supported Debian versions
-------------------------

So far packages were tested on following Debian versions:

- wheezy i386/amd64
- squeeze i386/amd64
- lenny i386/amd64

New users of Debian Wheezy should cosider using java-package:
<http://wiki.debian.org/JavaPackage>

Packages are compatible with the "official" Debian ones. However, I've
removed a lot of obsolete code (dating back to etch), licensing stuff
(since it does not apply anymore) and made general cleanups. For
details of changes see 'changelog' file.

I do not have resources to test packages on Ubuntu. However, if one
finds any problem on Ubuntu, feel free to report an issue and I will
try to resolve it.

Usage
-----

To create packages on your own:

- apt-get install dpkg-dev
- git clone git://github.com/rraptorr/sun-java6.git
- cd sun-java6
- download jdk-6u45-linux-i586.bin and jdk-6u45-linux-x64.bin from
  <http://www.oracle.com/technetwork/java/javasebusiness/downloads/java-archive-downloads-javase6-419409.html>
  (yes, both, no matter which version you will run)
- download jce_policy-6.zip from
  <http://www.oracle.com/technetwork/java/javase/downloads/jce-6-download-429243.html>
- on multiarch amd64 systems (Wheezy) one must add i386 architecture:
  dpkg --add-architecture i386 && apt-get update
- dpkg-buildpackage -uc -us
- install any missing packages that dpkg-buildpackage complains about
  and repeat

Legal
-----

Oracle does not permit to distribute repackaged binaries of Java, so
be advised that hosting any public repository with Java packages is
probably illegal (at least in some parts of the world).

On the other hand, this repository contains only scripts, that allows
one to repackage Oracle Java in Debian friendly way. No binaries are
or will be hosted.

Thanks
------

If this saved you some time you can thank me with some bitcoins:
1java6fKwMJs6Ay6xntBUKtCbGa9Qj9jE
