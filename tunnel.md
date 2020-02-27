Tunnel 1, one step 
```
# on laptop
ssh -D 127.0.0.7:8080 <host1>
```

Tunnel 2, two steps
```
# on laptop
ssh -L 127.0.0.8:8080:localhost:8989 <host1>
# on <host1>
ssh -f -T -n -N -D 8989 <host2>
```
