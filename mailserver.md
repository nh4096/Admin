### Concepts

MUA (Mail User Agent). Client software.

MTA (Mail Transfer Agent). Main of email network.

MDA (Mail Delivery Agent). Save mail to store.

SMTP (Simple Mail Transfer Protocal). Transfer mails between MTAs.

POP (Post Office Protocal). Fetch from store.

IMAP (Internet Mail Application Protocal). Fetch from store.

Common ports

| Protocol | Port | Secured Port |
| --- | --- | --- |
| SMTP | 25 | 465 |
| IMAP | 143 | 993 |
| POP3 | 110 | 995 |

### Postfix

Mail storage
* mbox
* maildir

Queues
* Incoming
* Active
* Deferred
* Corrupted

Address classes
* Local
* Virtual alias
* Virtual mailbox
* Relay

List user modified settings `postconf -n`


### Dovecot

Generate self-signed certs
```
vim /etc/pki/dovecot/dovecot-openssl.conf
rm /etc/pki/dovecot/certs/dovecot.pem
rm /etc/pki/dovecot/private/dovecot.pem
/usr/libexec/dovecot/mkcert.sh
```

Edit config files such that
```
$ sudo grep "^[^\#]" /etc/dovecot/conf.d/10-ssl.conf
ssl = required
ssl_cert = </etc/pki/dovecot/certs/dovecot.pem
ssl_key = </etc/pki/dovecot/private/dovecot.pem
ssl_protocols = !SSLv2 !SSLv3
```

Assemble settings from various config files `dovecot -n`.

