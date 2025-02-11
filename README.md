# vnc

## Start session
```
#apt-get install tigervnc-standalone-server
sudo apt install tightvnc*



cat<<EOF>>vnc.sh
#!/bin/bash

vncserver -geometry 1900x1080 -depth 16 -localhost no &
EOF

# On the remote
ssh -L8888:localhost:5901 vncserverip

vncviewer localhost:8888
```

## Kill session 
```
 vncserver -list

TigerVNC server sessions:

X DISPLAY #	RFB PORT #	RFB UNIX PATH	PROCESS ID #	SERVER
1         	5901      	             	24778       	Xtigervnc
bad@poseidon:~$ vncserver -kill :1
Killing Xtigervnc process ID 24778... success!

```
