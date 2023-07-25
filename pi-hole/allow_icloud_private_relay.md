# Allow iCloud Private Relay

Newer versions of Pi-hole [default](https://docs.pi-hole.net/ftldns/configfile/#icloud_private_relay) to blocking iCloud Private Relay. This is so that ad blocking and other privacy features of Pi-hole aren't bipased by Private Relay. To enable Private Relay on a network with Pi-hole, update the following:

```
BLOCK_ICLOUD_PR=false
```
