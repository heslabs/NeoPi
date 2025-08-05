# Debug

bind: address already in use

The "bind: address already in use" error indicates that a program or service is attempting to use a network port that is already in use by another process on the same machine. This can occur for several reasons: 

```
lsof -i:11434

COMMAND    PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
ollama  177056 demo    3u  IPv4 107047      0t0  TCP localhost:11434 (LISTEN)

kill -9 177056
```


---
### Troubleshooting and Resolution:

Identify the process using the port:
```
Linux/macOS: Use lsof -i :<port_number> or netstat -tulnp | grep <port_number> to identify the process ID (PID) and name of the application using the port.
```


```
ps aux | grep ollama
demo      176965  0.1  0.8 504064 141728 pts/0   Sl   17:33   0:00 konsole -e $SHELL -c "ollama serve; $SHELL"
```
