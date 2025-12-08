Needs libhwloc15
shell in and run

`sudo apt update`

`sudo apt install libhwloc15`

Custom link should install normal

Unfortuantely for now there is no hashrate reporting, that's just how this xmrig was compiled. If it gets updated I will try my best to get it working
Also please ignore $CUSTOM_LOG_BASENAME, no effects to the miner at all, this is my first wrapper

We do need to fix just one thing in the terminal, which is out wallet. For some reason I cannot get xmrig to pull wallet from template or using -u wallet. So we need to shell in

`cd`

`cd hive/miners/custom/junocash`

`ls` you should see a print ouf of these files: h-config.sh  h-manifest.conf  h-run.sh  h-stats.sh  xmrig

`nano h-config.sh` will open a window, look for "user": "$CUSTOM_USER", we will replace the $CUSTOM_USER with our wallet
![h-config before](https://github.com/BlessedNoob/Junocash-Hiveos/blob/d5966b1ff8103fdaa88fd47013b0ff80af0f8aa9/h-config%20before.jpg)
![h-config after](https://github.com/BlessedNoob/Junocash-Hiveos/blob/6023cbfe867837fcb75ea1f3a58ee520bca0845f/h-config%20after.jpg) 

Once you replaced your wallet, CTRL + X, to exit. Y, to save changes. Enter, to confirm and exit back to terminal

To make sure changes took just `nano h-config.sh` again, verify wallet is correct and CTRL + X. 

lastly run `miner resart` and it will refresh with wallet and start mining

Unfortunately we will need to this on every rig

![Miner Screen](https://github.com/BlessedNoob/Junocash-Hiveos/blob/56a72b9bd8ec03c33795af62d2220d0c80aa8e7d/Miner%20Screen.jpg)
