# Introduction #

This page will give information about how to build to software for your dongle, this page assumes a Linux based operating system is used.

# Details #

In order to build the software for the dongle the following two things are needed:

<ul>
<li>SDCC compiler</li>
<li>CC1111USB software</li>
</ul>

## SDCC compiler ##

The software is compiled using the SDCC (Small Device C Compiler). This compiler is open source and support the 8051 core that is included in the CC111x chips.

The version of this compiler that should definitely work is 2.9.0. This can be downloaded from [here](http://sourceforge.net/projects/sdcc/files/). Follow the included instructions to install the SDCC compiler.

## CC1111USB software ##

The CC1111USB software is the library provided on this site. Because a release isn't available yet the code has to be obtained from the repository.

The software can be checked out using the following command:
`svn checkout http://cc1111usb.googlecode.com/svn/trunk/ cc1111usb-read-only`

This command checks out the complete repository. The most stable firmware is located in `trunk/trunk/firmware`. Specific branches can be found in `trunk/branches/nameofbranch/firmware`. Branches are mostly in development process and are considered unstable.

In order to build the software, one of the following commands can be issued:
<ul>
<li>Chronos dongle <code>make</code></li>
<li>CC1111EMK <code>make donfw</code></li>
<li>IM-Me dongle <code>make immefw</code></li>
<li>Receive test <code>make testrecv</code></li>
<li>Transmit test <code>make testxmit</code></li>
</ul>

The resulting hex image is located in the `bin` folder and can be loaded into the dongle using a [CC Debugger](http://www.ti.com/tool/cc-debugger) or a [GoodFET](http://goodfet.sourceforge.net/).