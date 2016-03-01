
`docker-composer up -d`


```bash
$ printf "set mykey 0 60 4\r\ndata\r\n" | nc localhost 11211
STORED
$ printf "get mykey\r\n" | nc localhost 11211
VALUE mykey 0 4
data
END
$ printf "get mykey\r\n" | nc localhost 11212
VALUE mykey 0 4
data
END
$ printf "get mykey\r\n" | nc localhost 11213
VALUE mykey 0 4
data
END
$ printf "get mykey\r\n" | nc localhost 11214
VALUE mykey 0 4
data
END
$ printf "delete mykey\r\n" | nc 192.168.0.174 11211
DELETED
$ printf "get mykey\r\n" | nc 192.168.0.174 11211
END
$ printf "get mykey\r\n" | nc 192.168.0.174 11212
END
$ printf "get mykey\r\n" | nc 192.168.0.174 11213
END
$ printf "get mykey\r\n" | nc 192.168.0.174 11214
END
```