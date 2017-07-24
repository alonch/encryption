Encryption
=================

This post talks about the basic requirements to implement ``Transport Layer Security`` (**TLS**) and problems it solves

End-to-End encryption
--------------------

How are you sure that nobody is reading or changing what you send?

![](img/middleman-message.png)

This issue is solved by using **Public-Key cryptography**

#### How does it work? 

It consists in a pair of keys, ``public key`` and ``private key``

first, **public key** is used to **encrypt** messages

![](img/encrypt.png) 

then, **private key** is used to **decrypt** messages

![](img/decrypt.png) 


Trust Connection 
---------------------

How are you sure that there isn't another machine impersonating the host that you are trying to connect? 

![](img/middleman.png)

This issue is solved by using **Public-key certificate** also known as **Digital Certificate** or just **Certificate**

#### What is the **Certificate**?

The Certificate is basically a digital form of identification, where the public key is typically published with attached information, including the issuer. 

Certificates are created by a ```Certificate Authority``` (**CA**), a mutually trusted third party that confirms the identity of the certificate requestor. For instance, **VeriSign** and **GoDaddy** are two of the most populars

![](img/certificate.png)

#### How does it work? 

Instead of asking for the Public key of the remote host, it would ask for its **Certificate**

![](img/cert-issuer.png)

In order to accept the remote connection, the CA certificate should be known


File Formats 
---------------------


### .pem

Is a plain-text format that could contain the ``certificate`` and/or the ``private key`` and/or ``public key``

![](img/pem.png)

You can open .pem files in any text editor and check

#### Examples:

for **Private key**:

```
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAlJtuOybb2pxAGaANG7+9PJo19CMtmvtiHV9iooYkkxVy0dtufQkGbfO+wpmL
...
8PSYC1yUKL4HvrwNUyFIGp1SDgv9NecnXVXSns/lWWms2pEvJXtLdKAHdxgkNhDUBn/9XrgXAb0c
-----END RSA PRIVATE KEY-----
```

for **Public key**:
```
-----BEGIN PUBLIC KEY-----
MIIEpAIBAAKCAQEAlJtuOybb2pxAGaANG7+9PJo19CMtmvtiHV9iooYkkxVy0dtufQkGbfO+wpmL
...
8PSYC1yUKL4HvrwNUyFIGp1SDgv9NecnXVXSns/lWWms2pEvJXtLdKAHdxgkNhDUBn/9XrgXAb0c
-----END PUBLIC KEY-----
```

for **Certificate**: 

```
-----BEGIN CERTIFICATE----- 
MIIEpAIBAAKCAQEAlJtuOybb2pxAGaANG7+9PJo19CMtmvtiHV9iooYkkxVy0dtufQkGbfO+wpmL
...
8PSYC1yUKL4HvrwNUyFIGp1SDgv9NecnXVXSns/lWWms2pEvJXtLdKAHdxgkNhDUBn/9XrgXAb0c
-----BEGIN CERTIFICATE-----
```


### .pkcs12 .pfx .p12
Is a password protected file that contains the ``certificate`` and the ``private key``

![](img/p12.png)

To use .p12 files you will need to know the password


### .keystore .jks
Is a Java specific format, It is password protected and it contains .p12 data, the ``certificate`` and the ``private key``

![](img/jks.png)

To use .jks files you will need to know jks password and p12 password




Original Icons made by [Madebyoliver](https://www.flaticon.com/authors/madebyoliver)


