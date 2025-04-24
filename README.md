# NeoPi


#### Remote access to Neoverse edge server
```
$ sshpass -p rpi5demo ssh cx10@59.124.169.195 -X
$ cd ~/ollama-chat
$ ollama serve &
$ ollama run gemma3:27b $(cat ./quiz.txt)
```

#### quiz,txt
```
What is the difference between Cortex-A55 and Cortex-A53?
```
