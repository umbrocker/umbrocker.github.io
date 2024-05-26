# SSL/TLS
## TLS can be viewed as SSL v3.1 and compatible with SSL v3

- biztonságos és megbízható végpontok közötti adatátvitel

## az SSL 2 szintű protokoll:
- SSL session:
    - kliens-szerver közötti kapcsolat;
    - a Handshake protokoll által létrehozott kriptográfiai paraméterek készletét határozza meg;
    - több SSL-kapcsolat is megoszthatja.
- SSL connection:
    - átmeneti, egyenrangú (peer-to-peer), biztonságos kommunikációs kapcsolat;
    - egy SSL-munkamenethez kapcsolódik (abból származik);
    - egy munkamenet többször is használható kapcsolatok létrehozására.
- A session-öket arra használják, hogy elkerüljék a költséges kriptó paraméter egyeztetéseket minden egyes connection-höz

## Session state parameters (Munkamenet állapot paraméterei)
- Session identifier - munkamenet azonosító (szerver választja);
- Peer certificate - peer tanúsítvány: a partner entitás tanúsítványa (a kiszolgálóé, ha az entitás ügyfél, az ügyfélé, ha az entitás kiszolgáló)
- Compression method (to be deprecated in TLS v1.3)
- Cipher Spec
- Master Secret
- Is resumable

## Connection State Parameters
- Random numbers
    - server and client exchange
    - used as nonces during key exchange
- MAC secret
    - secret key used for MAC operations
    - Separate for server and client
- conventional encryption keys
- initialization vector (if CBC mode is used)

---

# Protocols used by SSL
## SSL Record Protocol
- uses connection parameters
- provides confidentiality and integrity
- also fragments (into 2^14 bytes chunks)
- optionally compresses data
- confidentiality: AES, IDEA, DES, 3DES, RC4, etc.
- message integrity (using HMAC with shared secret key)

## Change Cipher Spec Protocol
- very simple protocol
- the new state established by the handshake protocol is a pending state
- change cipher spec protocol (actually a single command exchanged between client and server) makes this pending state the current one
- will see its use in the handshake protocol

## Alert Protocol
- conveys SSL-alerts to peer entity (SSL-értesítéseket továbbít a másik egységnek)
- secured using the record protocol (if any)
- each message is two bytes
    - one byte for level (severity)
    - one byte for the alert code

## Handshake Protocol
- The most complex part of SSL
- Allows server and client:
    – to authenticate each other
    – to negotiate encryption and MAC algorithms
    – to create cryptographic keys to be used
    – in general, to establish a session and then a connection
- handshake is done before any data is transmitted
- a series of messages in 4 phases
    1. Establish Security Capabilities
    2. Server Authentication and Key Exchange
    3. Client Authentication and Key Exchange
    4. Finish

## Master Secret Creation
- 48-byte value generated for a session
- two stage creation
    - pre-master secret is exchanged during handshake
        - if RSA, client creates, encrypts and sends; server decrypts
        - if DH, both calculates the same secret which is the premaster secret
    - master secret is calculated using pre-master secret and random nonces exchanged during handshake

---

# Authentication Header (AH protocol)
## AH services:
- Authentication
- Integrity

![AH protocol](./image01.png)<br>
![AH packet](./image02.png)<br>

- Next header: This field involves information about the header following the AH header. 
- Security Parameter Index (SPI): It is an identifier that indicates to the receiver how to interprete the packet, what algorithms and keys should be used. AH assumes that the peers already negotiated all the parameters before with the help of ISAKMP/IKE protocol.
- MAC: Calculated hash value for the whole packet.

---

# Firewalls
## Packet filtering firewalls
- It works at layers 3 and 4
- The information provided in the packet header is compared to the firewall rules in a predefined order!
- If packet matches one of the rules, than the action is carried out based on the rule
- Does not handles connection states
- Provides low level security, because it does not analyses the payload of the packet
- Complex configuration
- Duplex traffic should be handled with two rulesets applied in the different directions
- There are some protocols that negotiates port numbers dynamically (FTP) in that cases port ranges should be enabled

## 2nd gen, Stateful firewalls
- Stateless packet filtering:
    - ACLs filter traffic based on source and destination IP addresses, TCP and UDP port numbers, TCP flags, and ICMP types and codes.
- Stateful packet filtering:
    - Inspection remembers certain details, or the state of that request.
    - Device maintains records of all connections passing through the firewall, and is able to determine whether a packet is the start of a new connection, or part of an existing connection.
    - A stateful firewall monitors the state of connections, whether the connection is in an initiation, data transfer, or termination state.
- A packet-filtering firewall typically can filter up to the transport layer, while a stateful firewall can filter up to the session layer.

## Application level firewalls
- Two subcategories:
    - Proxy Firewalls
    - Deep Packet Inspection Firewalls
- Operate at the 7th layer of the OSI model
- Advantages:
    - High level security
    - Easier to configure than packet filter firewalls
- Disadvantages:
    - High CPU load
    - Vendors should follow new protocols
    - No transparency (with proxy)

### Proxy firewalls
- It runs Proxy applications, that create separate connections with the two communicating parties.
- The indirect connections breaks, the proxy gateway recreates the packets that should be forwarded, with copying the required protocol fields.
- For every application type a separate proxy server is needed. HTTP proxy recreates only HTTP traffic fields.
- It can affect functionality and speed

### Deep packet inspection firewalls
- It works transparently, does not set up connections with the two communicating parties.
- Filters in all 7 layers of the OSI mode
- Filters the packets that are not appropriate according the protocol
- Categorizes the packets according to different applications: Skype, Bittorrent, Webex, etc.
- It can provide IDS and IPS as well
- With DPI custom rules can be defined by the company, it can be set which applications workers can interact with.
- DPI gives the visibility to administrators over the entire network.
- It can be used to inspect data outbound, to prevent data exfiltration



