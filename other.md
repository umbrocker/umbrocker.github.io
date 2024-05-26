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

## SSL Record Protocol
- uses connection parameters
- provides confidentiality and integrity
- also fragments (into 2^14 bytes chunks)
- optionally compresses data
- confidentiality: AES, IDEA, DES, 3DES, RC4, etc.
- message integrity (using HMAC with shared secret key)


