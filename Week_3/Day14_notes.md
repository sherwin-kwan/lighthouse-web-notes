## Day 14 - 1 Oct 2020

### Agenda

* Network Security

### Encyrption and Hashing

* Passwords have to be hashed (one-way encryption) to make sure that no one can steal them
* A hash algorithm turns plain text into a random string, and it is not possible to turn it back into plain text
* To check if a password is correct, hash the attempted password to see if it matches the original hash
* Similarly, normally websites use cookies to determine whether or not you're a particular user. If cookies are stored in plain text, it's trivial for a user to change the cookie in order to pass themselves off as someone else (which would defeat the purpose of having passwords)
* For this reason, cookies need to also be encrypted. Each server will normally have one or more *secret keys* which are used to encrypt and decrypt cookies
* Therefore, do not under any circumstances reveal a secret key on Github. Put it in a separate file and .gitignore it

### Types of Encryption

* Some algorithms for encryption are symmetric: the same key will both encrypt and encrypt a message
* Other algorithms are asymmetric: one key encrypts a message, and a corresponding key decrypts it
* HTTPS (built on TLS) uses an asymmetric algorithm. There is a public key that everyone knows, which is used to encrypt the data you're sending on the Internet, and then there is a private key that only the recipient has, which decrypts it
* This prevents the *man-in-the-middle attack*, in which an attacker compromises a gateway (a computer that's along the way between the server and client, which relays the message between the two)
  * One common way is to take advantage of someone who's using an unsecured WiFi access point, it's fairly easy to impersonate someone else on the same WiFi network since the IP address will match
  * However the means, eventually the attacker injects themselves into a conversation between A and B, and is able to convince A that they are B, and convince B that they are A, and thus obtains secret information from A that is only supposed to go to B (or vice versa)


### REST (Representational State Transfer)

* A system of designing web applications, in which all actions can be taken with a request to the server with a standardized format

### Asynchronous Code

* Remember, hashing is a process that takes time, you have to use callbacks or "synced" versions of those functions

### Hafiz's Tips

* To check if *X* is part of an array *Y*, use the predicate (Y.indexOf(X) > -1)
