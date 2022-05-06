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
<<<<<<< HEAD
mwhois is server software compatible with the whois(1) command
on most Linux and Unix systems.  It is  fully compliant with the
RFC 3912. It can serve domain name and  IPv4  whois records when
queried and uses a Linux / Unix filesystem structure for storing
all the records. 
=======
mswhois is a simple proof of concept to serve whois from CSV.
This program loads all records from a csv-file, and only supports
IPv4 and IPv6 allocations and assignments.
The column order isn't relevant, as the file is loaded with 
the header names intact, via DictReader (python library).
>>>>>>> origin/ram-backend

Requirements:
- Python3 (tested on, might work funny on python2.x) 
- netaddr, 

License:
<<<<<<< HEAD
The project is under the MIT License on its whole,  except from
the "netaddr" python library that has a separate license, which
is included in the respective folder.  The library  is included
in order to ensure compatibility and is updated when deemed
necessary.
=======
This project is licensed under the AGPL, so you have to show
what kind of software you run for your service.
>>>>>>> origin/ram-backend

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

<<<<<<< HEAD
Storage Structure:
The database that is served by mwhois is using the Linux / Unix
filesystem in order to store content. There is a  folder  named
"db" with two primary sub-folders, "ipv4" and "domains". In the
first folder, all whois content for IPv4 Addresses is  located,
and in the second folder, there is all the  whois  content  for 
the domain names. All IPv4 records are stored  in  files  named
after the IP Address  CIDR  Block.  For  example,  the  network
10.0.0.0/8 is stored in a file named 10.0.0.0-8  that  contains
all the information that will be served. All the new  lines  in
this file must be represented by <CR><LF> in order to  maintain
full compatibility with RFC 3912. As far as  domain  names  are 
concerned, the storage is similar, where the name of  the  file 
is the actual domain name.
=======
>>>>>>> origin/ram-backend
