Chaosreader
===========

Chaosreader is an any-snarf program that processes application protocols (HTTP/FTP/...) from tcpdump or snoop files and stores session and file data. Rip files from network sniffing dumps.

This was originally written as a security demonstration tool, proving that unencrypted protocol types including telnet, X11, and VNC, can be reassembled and replayed from network packet dumps. This was the first tool to capture and replay VNC, and one of only a few to attempt X11.

Various protocols and file transfers are supported, including telnet sessions, FTP files, HTTP transfers (HTML, GIF, JPEG, ...), SMTP emails, X11 sessions, VNC sessions, etc. Chaosreader creates a html index file that links to all the session details, including realtime replay programs for telnet, rlogin and IRC sessions; and reports such as image reports and HTTP GET/POST content reports.  It also creates replay programs for telnet sessions, so that you can play them back in realtime (or even different speeds).

Chaosreader can also run in standalone mode - where it invokes tcpdump or snoop (if they are available) to create the log files and then processes them.

This is an updated fork of my original [chaosreader](http://www.brendangregg.com/chaosreader.html), and includes patches by Jens Lechtenbörger http://www.informationelle-selbstbestimmung-im-internet.de/chaosreader.html and others.

### Internals

This is a stand-alone Perl program that reads binary tcpdump/snoop files, and performs both TCP and IP-fragment reassembly.

I've had many thank-you emails to say people appreciated the convenience of this being a stand-alone script, which doesn't require various CPAN modules. Yes, it's convenient, but there was also nothing on CPAN to do raw TCP packet processing and session reassembly, or raw IP packet processing and IP fragment reassembly.

### Patches:

* Handling `Content-Encoding: deflate`
