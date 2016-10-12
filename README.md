ShatteredGlass
==============

_Information Sharding for Universal Information Storage utilizing Universal Information Identifiers_
----------------------------------------------------------------------------------------------------

Overview
========

ShatteredGlass uses *Information Sharding* to shatter information bit
strings into Shards for persistence in a *Universal Information Storage
Container*. No central authority is required to manage namespaces,
information owners, and information sharing. *Information Sharding* has
the following properties:

1.  *Universal Information Identifiers* (UII, pronounced yōō'ē)
    provide unique information identity without the need for a central authority.

2.  Information is shattered (sharded) into one or more *Shards*.
    Authenticated encryption ensures shard privacy and integrity.

3.  *Information Dispersal Algorithms* ([Erasure Coding](http://en.wikipedia.org/wiki/Erasure_code))
    are optionally used for [data redundancy](https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction)
    that provides resistance to shard loss and enables *Information* *Horse Racing* and *Information
    Quorums*.

4.  Cryptographic primitives are based on sponge functions, specifically
    the [Keccak](http://keccak.noekeon.org/) family
    of sponge functions used for [permutation-based hashing](https://www.nist.gov/node/555116?pub_id=919061),
    message authentication, authenticated encryption, and hash-based signatures [1].

5.  *Shard Servers* are unaware of shard contents, are unaware of shard
    interrelationships, and are unaware of shard ownership. No knowledge
    is obtained by analyzing the Shards stored on shard servers [2].
    Privacy and anonymity is maintained.

6.  Information Sharding, when used in conjunction with anonymity
    networks such as the [Tor network](https://www.torproject.org), is resistant to file-size
    analysis and traffic analysis.

Information Sharding is built upon ideas from cryptography, erasure
coding, distributed computing, and git. I believe five aspects of
Information Sharding are unique to this ShatteredGlass specification:

1.  The definition of *Information Sharding*.

2.  The definition of a *Universal Information Identifier*.

3.  Using cryptographic algorithms to derive—rather than
    store—shard UIIs. The information owner or group computes the
    identity of any information shard at runtime. It is computationally
    intractable for an attacker to deduce shard relationships.

4.  Shard Server simplicity; servers simply need to store shards by UII
    and return shards by UII. All other processing is performed on
    the client.

5.  The ability to optionally transform shards, for example, into image
    files such as Portable Network Graphic (PNG) files, for storage on
    cloud-based image storage services such as Google Photos or
    Facebook. I have successfully stored 100's of GB of data without
    additional cost on a 15GB-limit free Google Photos account.

I have created a version of ShatteredGlass written entirely in
Javascript running on [Node.js](https://nodejs.org). This implies that
ShatteredGlass can run on any client computer that supports web technology
including [Tails](https://tails.boum.org) and secure boot tokens such as
the [USB Armory from Inverse Path](https://inversepath.com/usbarmory).

The system can store shards either on a standard
local file system, on a [Hadoop](http://hadoop.apache.org) storage cluster, in an email
system such as Gmail, on a cloud storage system such as Amazon S3 or
Google Cloud, on a photo sharing cloud service by masquerading
the shards as well-formed PNG files (Google Photos), or even here on
GitHub.

ShatteredGlass: anonymous and private information publicly hiding in plain sight.

Source Code
===========

The current source code is sharded in the Shards directory and a
duplicative PNG image version sharded in the ShardsPNG directory.

The source code will remain sharded until the ShatteredGlass specification
is completed and uploaded to this GitHub project.

Shards
------

Created Owner[C4455A0965642FDFEFE47A2D62D5C9CFF9AE605C17A455C928096D5D6EE6A025]

Stored UII[423490945E6A7DB03B1B57CCF961B2B2C8B280BEADDD3DE7B77AFAE506B12BAB]

ShardsPNG
---------

Created Owner[39524183F9206E23F1E440BAFB0B3C02AF3154C2239BC29C07350C3441D870D4]

Stored UII[956B40A6A1F9B94D23297A66F13A0F238E915DDA6C31A4EFFB90689DA39C3E39]

Footnotes
=========

[1] I adopted hash-based signatures because of their resistance to Quantum Computing attacks.

[2] Hopefully leaving Shard Server operators legally immune to data sharing prosecution.
