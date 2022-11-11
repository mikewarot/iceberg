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
    Where it should go
	  Public
	  Friends
	  Work
	  other
- Message Signature
	 
	 
Encrypted Messages include
  -- NOT SENT - AES key
  -- AES encrypted data
  -- RSA encrypted copies of the AES key, one per destination

