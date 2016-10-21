ShatteredGlass
==============

_Information Sharding for Universal Information Storage utilizing Universal Information Identifiers_
----------------------------------------------------------------------------------------------------

Overview
========

ShatteredGlass uses *Information Sharding* to shatter information bit
strings into *Shards* for persistence in a *Universal Information Storage
Container*. No central authority is required to manage namespaces,
information owners, and information sharing. *Information Sharding* has
the following properties:

1.  The *Universal Information Identifier* (UII, pronounced yōō'ē)
    provides unique information identity without the need for a central authority.

2.  Information is shattered (sharded) into one or more *Shards*.
    Authenticated encryption ensures shard privacy and integrity.

3.  *Information Dispersal Algorithms* ([Erasure Coding](http://en.wikipedia.org/wiki/Erasure_code))
    are used for [data redundancy](https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction)
    to provide resistance to shard loss and enable an *Information* *Horse Race* and an *Information
    Quorum*.

4.  Cryptographic primitives are based on sponge functions, specifically
    the [Keccak](http://keccak.noekeon.org/) family
    of sponge functions used for [permutation-based hashing](https://www.nist.gov/node/555116?pub_id=919061),
    message authentication, [authenticated encryption](http://keyak.noekeon.org/),
    and [hash-based signatures](http://csrc.nist.gov/groups/ST/post-quantum-2015/papers/session5-hulsing-paper.pdf) [1].

5.  *Shard Servers* are unaware of shard contents, are unaware of shard
    interrelationships, and are unaware of shard ownership. No knowledge
    is obtained by analyzing the Shards stored on shard servers [2].
    Privacy and anonymity is maintained.

6.  Information Sharding, when used in conjunction with anonymity
    networks such as the [Tor network](https://www.torproject.org), is resistant to file-size
    analysis and traffic analysis.

Information Sharding is standing on the shoulders of concepts in Cryptography,
Erasure Coding, Distributed Computing, and Git. Five aspects of
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
    cloud-based image storage services such as [Google Photos](https://photos.google.com)
    or [Facebook](http://www.facebook.com). ShatteredGlass has successfully stored
    100's of GB of data without additional cost in a single 15GB-limit free
    Google Photos account.

ShatteredGlass is written entirely in Javascript running on [Node.js](https://nodejs.org)
and can run on any client computer that supports web technology
including [Tails](https://tails.boum.org) and secure boot tokens such as
the [USB Armory from Inverse Path](https://inversepath.com/usbarmory).

ShatteredGlass can store shards either in a standard
local file system, in a [Hadoop](http://hadoop.apache.org) storage cluster, in an email
system such as [Gmail](http://gmail.com), in a cloud storage system such as
[Amazon S3](https://aws.amazon.com/s3) or [Google Cloud](https://cloud.google.com/storage),
in a photo sharing cloud service such as [Google Photos](https://photos.google.com) by masquerading
the shards as well-formed PNG files, or even in [GitHub](https://github.com/Lanovaz/shattered-glass).

ShatteredGlass enables information to publicly hide in plain sight.

Source Code
===========

ShatteredGlass source code is sharded into the Shards directory and a
duplicative PNG image version sharded in the ShardsPNG directory.

ShatteredGlass source code will remain sharded until specification review
is completed and an initial version is uploaded to this GitHub project.
At that time the key to unlock the shards may be uploaded to GitHub.

Shards
------

Created Owner[1709340E69AD70C98E07499AB9144BF410581C037F5D60CF90FF0D4BEA508F89]
Stored UII[98D3E0C6B4DCCDB35460D4882AF7EA0731767EAAB46F9708822DA6B0A26E8779]

ShardsPNG
---------

Created Owner[24F675C842590E63DF578D1B997B3DB477D211EB6C2CC7FBA311A7472C6A60A3]
Stored UII[C39E07B4D43BB111C3DDF3876AB17B46F62CD0E573C8AC8CB83E15D656ECF9E8]

Footnotes
=========

[1] Hash-based signatures are used because of their resistance to Quantum Computing attacks.

[2] Shard Server operators will hopefully be legally immune to data sharing prosecution
from entities such as the MPAA.
