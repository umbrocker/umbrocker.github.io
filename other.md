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