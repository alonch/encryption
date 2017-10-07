Is Encryption necessary?
===================

I'm surprise how people underestimate the importance of secure connections, from Industrial Systems to Call Centers, the majority of industries trust that network security is enough.

We all agree that network security when done right is perfect, well, most of the time. The catch is that security is an ongoing task and a simple misconfigure firewall could open a door enough time for intruders to get inside.

Once the network is compromise, it is just a matter of time for hackers to scan and find backdoors. Once a malicious software is running within the network, messages could be intercept and even replace by completely new ones.

![](img/middleman-message.png)


Encryption
--------------

Most IT infrastructure like emails, browsers and instant message, use Transport Layer Security `TLS`. It adds another level of security, where messages can **only** be interpreted by the destinatary, let's see how it works.

It consists in a set of passwords, one password is shared to everybody, so they can send messages that can only be understand using the other password, for instance:

Let's assume that **Alice** wants to send the message to **Bob**.   
She uses Bob's password to encrypt her message  

![](img/encrypt.png) 

When **Bob** receives the message, he decrypts the message using the password that only he knows

![](img/decrypt.png) 


Trust Connection
--------------

There is another problem, so far everything works perfectly once the connection has been established. However, we still need to face the handshake phase.  

Computers are just IP address `172.217.9.78` and there are services routing your network packages to the right host. How are you sure that you are connection to the right party? 

![](img/middleman.png)

In order to overcome this limitation, digital certificates are used. 

Certificates are created by a Certificate Authority, a mutually trusted third party that confirms the identity of the application, **VeriSign** and **GoDaddy** are two of the most popular. Certificates hold information about issuer and host, including his public password. 

Now, applications don't care where they are connecting to, as long as the provide the right certificate 

![](img/cert-issuer.png)


Original Icons made by [Madebyoliver](https://www.flaticon.com/authors/madebyoliver)
