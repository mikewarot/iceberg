# Iceberg - Design decisions log

## 11/11/2022 Day 1 of 13

- Prototype that works on Windows and Linux from the command line by Thanksgiving, 11/24/2022
- Markdown for this log file, and things like it... it's popular on the internet
- AES encryption for private messages, RSA for the keys, allow NSA or whoever along with the recpient to read the message by separately encrypting the AES key for that message to each one (like PGP does, I think)
- We have to build in allowing the NSA or someone else to read encrypted messages, along with recipients
  I know this seems like a bad decision, but it's better to do that stuff in the open, in my opinion

### Message format, etc.
  This is the hard one... there's JSON or XML or something off the wall, and I don't know what's best
  Email uses none of those, and it works ;-)
  
Let's brainstorm...

A message includes

- Creation Timestamp
- Creator ID
- Actual bytes of content *or encrypted bytes*
- Destination designations such as
  - Where it should go
	- Public
	- Friends
	- Work
	- other
- Message Signature
	 
	 
Encrypted Messages include
- NOT SENT (Temporary in memory) AES key
- AES encrypted data
- RSA encrypted copies of the AES key, one per destination

## 11/12/2022, Day 2 of 13 -- My Birthday  8)

Wow... there are a ton of P2P examples out there for Python, and a lot of code for almost everything.
This is the exact opposite of the 1980s and Turbo Pascal, where you'd have to implement everything yourself.

I'm going to avoid trying to punch holes in NAT routers, stick with IPV4 for now, and manually open a port
in my router once I decide to test across the actual internet.

It seems that SQL-lite is the way to go for local database stuff. The local Web UI is going to be one of the tricky bits
