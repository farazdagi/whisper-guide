*******************
Introduction
*******************

Whisper is an identity-based messaging system.

Whisper provides a low-level (non-application-specific) but
easily-accessible API without being based upon or influenced by the low-level hardware attributes and characteristics.

Peer-to-peer communication between nodes running Whisper clients uses the underlying ÐΞVp2p Wire Protocol. Whisper was
not designed to provide a connection-oriented system, nor for simply delivering data between a pair of particular
network endpoints. Whisper is designed for easy and efficient broadcasting, and also for low-level asynchronous communications.

For some specific cases endpoint-to-endpoint message delivery might be necessary (e.g. delivering the expired messages in
case they were missed), and Whisper protocol will accommodate for that.

Whisper is designed to be a building block in next generation ÐApps which require large-scale many-to-many data-discovery,
signal negotiation and modest transmissions with an absolute minimum of fuss and the expectation that one has a very
reasonable assurance of complete privacy.

At its most secure mode of operation, Whisper can theoretically deliver 100% darkness (at a considerable cost of bandwidth and
latency). Whisper should also allow the users to configure the level of privacy (how much information it leaks
concerning the ÐApp content and ultimately, user activities) as a trade-off for performance.

Protocol Overview
====================

Whenever a Ðapp needs to broadcast a message over Whisper network, it creates an encrypted message, wraps it into envelope,
seals envelope by spending time as PoW, and finally adds the message to message pool on a local node.
The message then gets retransmitted to peer nodes, up until message's TTL is reached.

Basically, all Whisper messages are supposed to be sent to every Whisper node. In order to prevent a DDoS attack,
proof-of-work (PoW) algorithm is used. Messages will be processed (and forwarded further) only if their PoW exceeds a
certain threshold, otherwise they will be dropped.


Messages
====================

Envelopes
====================
