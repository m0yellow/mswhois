mswhois by Matthias Šubik in 2020

based on the idea of
mwhois 
by Antonios A. Chariton <daknob.mac@gmail.com>

I read through his great project, and decided I need to
learn all those data types. By the way I replaced everything
up to no recognition. I have a different goal:
an IPv4/IPv6 whois server from RAM for internal use.
For me it works with an internal database of about 5k lines.
I could even save more RAM by loading only the columns 
printed in whois, but this way it could easily changed to 
show more. 
To not taint the original work, I did make it a related project,
not a fork or something similar.

Description: 
mswhois is a simple proof of concept to serve whois from CSV.
This program loads all records from a csv-file, and only supports
IPv4 and IPv6 allocations and assignments.
The column order isn't relevant, as the file is loaded with 
the header names intact, via DictReader (python library).

Requirements:
- Python3 (tested on, might work funny on python2.x) 
- netaddr, 

License:
This project is licensed under the AGPL, so you have to show
what kind of software you run for your service.

Usage:
run the server from your command line as 
$ python3 mswhois.py
The whois server can be contacted by whois(1), but I found
one that segfaulted with this whois server. Ooops. 
Netcat or telnet(1) work fine too.
Example: whois -h 127.0.0.1 -p 8043 10.10.10.10

Configuration:
You can find the configuration in the program for now,
as constants in the header.

