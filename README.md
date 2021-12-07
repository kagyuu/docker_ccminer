# docker_ccminer

## What is this?
* This is a mining rig container for crypt currency.

## How to use it?

```
$ docker-compose up --build

Starting docker_ccminer_ccminer_1 ... done
Attaching to docker_ccminer_ccminer_1
ccminer_1  | *** ccminer 2.3.2 for nVidia GPUs by tpruvot@github ***
ccminer_1  |     Built with the nVidia CUDA Toolkit 11.4 64-bits
ccminer_1  | 
ccminer_1  |   Originally based on Christian Buchner and Christian H. project
ccminer_1  |   Include some kernels from alexis78, djm34, djEzo, tsiv and krnlx.
ccminer_1  | 
ccminer_1  | BTC donation address: 1AJdfCpLWPNoAMDfHF1wD5y8VgKSSTHxPo (tpruvot)
ccminer_1  | 
ccminer_1  | [2021-12-07 16:09:37] Starting on stratum+tcp://sha256.jp.nicehash.com:3334
ccminer_1  | [2021-12-07 16:09:37] 1 miner thread started, using 'sha256d' algorithm.
ccminer_1  | [2021-12-07 16:09:37] Stratum difficulty set to 65098.2
ccminer_1  | [2021-12-07 16:09:37] sha256d block 717346, diff 204381958504.133
ccminer_1  | [2021-12-07 16:09:38] GPU #0: Intensity set to 25, 33554432 cuda threads
ccminer_1  | [2021-12-07 16:09:40] GPU #0: NVIDIA GeForce RTX 2070, 1640.17 MH/s
ccminer_1  | [2021-12-07 16:09:45] GPU #0: NVIDIA GeForce RTX 2070, 1641.00 MH/s
ccminer_1  | [2021-12-07 16:09:51] GPU #0: NVIDIA GeForce RTX 2070, 1635.59 MH/s
ccminer_1  | [2021-12-07 16:09:56] GPU #0: NVIDIA GeForce RTX 2070, 1632.39 MH/s
ccminer_1  | [2021-12-07 16:10:01] GPU #0: NVIDIA GeForce RTX 2070, 1623.34 MH/s
ccminer_1  | [2021-12-07 16:10:06] GPU #0: NVIDIA GeForce RTX 2070, 1622.73 MH/s
```
* You can stop ccminer with Ctrl+C.

# Attach your bitcoin wallet.

* Change docker-compose.yml
```
command: /root/ccminer/ccminer -a sha256d -o stratum+tcp://sha256.usa-west.nicehash.com:3334 -u 35wXssceVET45koSKXA93g6YKdfiMEzyDY
```
* You don't have to sign in to nicehash. This is an address of NOMP (Node Open Mining Potal).
* Set your wallet ID to argument "-u". (The 35w...yDY is my wallet :-P)

# More 

* You can use MPOS insted of NOMP:
  * The nicehash is a mining pool. This URL is a NOMP (Node Open Mining Portal). You can use it without creating account.
  * You can also use MPOS(Mining Portal Open Source). MPOS has some usefull dashboards. You can reconginze how many Bit coins your gpu earned easily rather than NOMP.
* If you want to start mining with the power on, enable the flag "restart: always" on the docker-compose.yml. 