## xTIntranet - LAN Gaming over EACCESS
LAN Gaming over Thapar's Wifi (EACCESS, etc) made possible :)!!
### Why?
Cause why not? Who doesn't want to play with their pals and enjoy a fun gaming session together? All without any hassles of hosting global servers or gathering into one room to allow for LAN gaming over mobile hotspots/ethernet!

* Conventional Access to LAN is blocked, so you can't play multiplayer lan games over eaccess the same way you do with your mobile hotspots!
* One PC can't access another over localhost (intranet) normally over EACCESS wifi (Yes it's blocked).
* Cannot expose localservices over thapar wifi.
* Get super low ping because you are using Intranet to play games.
#### Limitations
* **Limited to single Hostel, ie Hostel M can't play with gamers from Hostel O or Hostel N**.
* Prototype/Alpha stage - not widely tested, might still contain some bugs.
* A little difficult for total tech beginners (don't worry, I will help y'all).
* *Need friends to play with*... (jk)

https://user-images.githubusercontent.com/31770598/147371065-875a2f78-4088-4b2f-80ee-8e1b3f728a1d.mp4


## Step-By-Step
1. Clone the backbone repository [project-orion](https://github.com/hari01584/project-orion)
```
git clone https://github.com/hari01584/project-orion
```
2. Install requirements and cd to /sirius
```
cd project-orion
python -m pip install -r requirements.txt
cd sirius
```
3. Run get.py to download neccesary files for running this project.
python get.py
```
python get.py
```

**EXAMPLE PLAYING MINECRAFT JAVA OVER LAN**

Minecraft is an easy to accessible and fun game, here further steps are taken with regards of setting Minecraft World for LAN play, Similar steps are to be taken for other games as well (like CSGO, L4D2, NFS, etc)

***STEPS***

1. Open Minecraft, Create a single player world and select *Open for LAN* option from menu, the game will output an important numeric value (or port of hosting server), *here it is 14259*
![game_open_lan](https://raw.githubusercontent.com/hari01584/xTIntranet/main/game_open_lan.png)

2. On this Host Server (Where LAN is exposed) run this command in project-orion/sirius directory

**NOTE: Your windows might give Virus Warning when executing frpc executable, but fret not it is a false positive report, all the projects/codes used in this project are open sourced and do not contain any malicious script/etc, the issue created for this [false positive report is here](https://github.com/fatedier/frp/issues/2095)**

```
python cli.py --no-host expose --tcp 14259
```
See how we used 14259 in the command, change this to your respective port number given in Step 1.

Check for it's output, make sure everything is working fine and there's no error! In case everything fine *note the secret_port* here its *24721*
![get_secret_port](https://raw.githubusercontent.com/hari01584/xTIntranet/main/get_secret_port.png)

3. Note the Host Server IPv6 Address (do ipconfig in windows or ip a in linux)
```
ipconfig /all
```

Here for example my host server IPv6 is *fe80::1c18:4d43:4031:1c81* (ignore % and everything after, its not in ipv6).
![see_ipv6](https://raw.githubusercontent.com/hari01584/xTIntranet/main/see_ipv6.png)

4. On your friend's PC (Connected to EACCESS obviously)  run this command in project-orion/sirius directory
```
python cli.py --no-host --host fe80::1c18:4d43:4031:1c81 connect 14259
```
![connect_secret_port](https://raw.githubusercontent.com/hari01584/xTIntranet/main/connect_secret_port.png)

*Now you can connect to ip *127.0.0.1:14259* in Minecraft and play on the server! :DD*

![local_connect_client](https://raw.githubusercontent.com/hari01584/xTIntranet/main/local_connect_client.png)

## Video (YT Full)
[![Alt text](https://img.youtube.com/vi/dvy7OiLBpoo/0.jpg)](https://www.youtube.com/watch?v=dvy7OiLBpoo)


## Feedback

If you have any feedback, please reach out at hari01584@gmail.com or preferably discord **Agent_Orange#9852**

Additionally create issues for anything faced in this method, please remember this is not tested for variety of devices and networks, so it might just fail, In that case you can contact me *I would love to help you setup local gaming sessions (and prolly love to join-in as well :P)*
