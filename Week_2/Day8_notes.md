## Day 8 - 23 Sep 2020

### Protocols

* Protocols are recognized, standard methods of doing things. In the Internet context, we are looking at standard methods for how computers communicate.
* The Internet has a number of layers. There are low-level layers like the physical infrastructure that allows computers to communicate.
* However, for the purposes of this course, we shall assume that there is functional low-level infrastructure, and only concern ourselves with the "application layer"
* Examples of protocols: POP3, IMAP, SMTP (email protocols), FTP, DNS, IP

### TCP

* Purpose: Divides a series of data (say, a webpage or piece of code) into small packets that can be sent over IP to another computer, and re-assembles them at the other end
* It is focused on accuracy over speed. In cases of congestion, TCP prefers to ensure that the page is delivered perfectly even if it takes a little longer.
* More specifically, TCP waits until the receiving end has confirmed receipt of a packet before it delivers the next one. (By contrast, UDP does not)
* Packets are sent to a particular *port* at an *IP address* (computer, server, etc.)
* TCP is the protocol of choice for sending webpages, webapps, etc. to a client. However for other applications where speed is more important than fidelity (say, video calls). use another protocol

### HTTP

* HTTP allows you to send or receive data, it's built on TCP
* Types of HTTP requests: 
  * GET ("give me some data")
  * POST("here's some data to send you") <-- Potentially unsafe. Often used for submitting forms.
  * PUT("change this piece of data") <-- It's unsafe!!
  * DELETE("delete this piece of data") <-- It's unsafe!!
* After a request is received by a server, it will respond with a response code
  * 200: OK. Things are normal.
  * 404: The resource you're looking for can't be found.

