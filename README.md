Chaosreader
===========

Chaosreader is an any-snarf program that processes application protocols (HTTP/FTP/...) from tcpdump or snoop files and stores session and file data. Rip files from network sniffing dumps.

This was originally written as a security demonstration tool, proving that unencrypted protocol types including telnet, X11, and VNC, can be reassembled and replayed from network packet dumps. This was the first tool to capture and replay VNC, and one of only a few to attempt X11.

Various protocols and file transfers are supported, including telnet sessions, FTP files, HTTP transfers (HTML, GIF, JPEG, ...), SMTP emails, X11 sessions, VNC sessions, etc. Chaosreader creates a html index file that links to all the session details, including realtime replay programs for telnet, rlogin and IRC sessions; and reports such as image reports and HTTP GET/POST content reports.  It also creates replay programs for telnet sessions, so that you can play them back in realtime (or even different speeds).

Chaosreader can also run in standalone mode - where it invokes tcpdump or snoop (if they are available) to create the log files and then processes them.

This is an updated fork of my original [chaosreader](http://www.brendangregg.com/chaosreader.html), and includes patches by Jens Lechtenbörger http://www.informationelle-selbstbestimmung-im-internet.de/chaosreader.html and others.

### Dependencies

This is a Perl program that reads binary tcpdump/snoop files, and performs both TCP and IP-fragment reassembly. It originally required no additional CPAN modules, in part, because the modules I really wanted (TCP and IP packet processing) didn't exist, and also for the convenience. Some CPAN modules have since been added in the latest version. 

If dependencies are a problem, see the older version under older_versions/chaosreader0.94.

### Patches:

* Handling `Content-Encoding: deflate`
