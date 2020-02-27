### Self-signed
```
# generate cert and key
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout selfsigned.key -out selfsigned.crt

# generate dh
openssl dhparam -out dhparam.pem 2048

# view cert
openssl x509 -text -noout -in selfsigned.crt

# is the key valid?
openssl rsa -check -noout -in selfsigned.key

# verify crt and key are in-pair
openssl rsa -noout -modulus -in selfsigned.key | openssl md5
openssl x509 -noout -modulus -in selfsigned.crt | openssl md5

# pem to der
openssl x509 -in foo.crt -outform der -out foo.der
```
