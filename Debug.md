# Debug

bind: address already in use

```
lsof -i:11434

COMMAND    PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
ollama  177056 demo    3u  IPv4 107047      0t0  TCP localhost:11434 (LISTEN)

kill -9 177056
```
