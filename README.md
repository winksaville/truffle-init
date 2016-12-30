# The project created using truffle init

This project is created using truffle init project:
```
mkdir truffle-init
cd truffle-init
truffle init
```
See [Truffle Framework](https://truffleframework.com) and specifically the [docs](http://truffleframework.com/docs/)
for more details.

Next you'll want a test blockchain and client, the easiest method
I've found is to install [testrpc](https://github.com/ethereumjs/testrpc) as
recommended in the truffle framework docs. But in that
documenation they don't actually tell you how/when to start testrpc client.
Turns out you can start it anytime before issuing a `truffle migrate` command
so now is a good time. And to start it just type its name after being installed.
I also used the -d parameter and gave it a name so the accounts are always
generated with the same addresses and keys:
```
$ testrpc -d truffle-init
EthereumJS TestRPC v3.0.3

Available Accounts
==================
(0) 0x90f8bf6a479f320ead074411a4b0e7944ea8c9c1
(1) 0xffcf8fdee72ac11b5c542428b35eef5769c409f0
(2) 0x22d491bde2303f2f43325b2108d26f1eaba1e32b
(3) 0xe11ba2b4d45eaed5996cd0823791e0c93114882d
(4) 0xd03ea8624c8c5987235048901fb614fdca89b117
(5) 0x95ced938f7991cd0dfcb48f0a06a40fa1af46ebc
(6) 0x3e5e9111ae8eb78fe1cc3bb8915d5d461f3ef9a9
(7) 0x28a8746e75304c0780e011bed21c72cd78cd535e
(8) 0xaca94ef8bd5ffee41947b4585a84bda5a3d3da6e
(9) 0x1df62f291b2e969fb0849d99d9ce41e2f137006e

Private Keys
==================
(0) 4f3edf983ac636a65a842ce7c78d9aa706d3b113bce9c46f30d7d21715b23b1d
(1) 6cbed15c793ce57650b9877cf6fa156fbef513c4e6134f022a85b1ffdd59b2a1
(2) 6370fd033278c143179d81c5526140625662b8daa446c22ee2d73db3707e620c
(3) 646f1ce2fdad0e6deeeb5c7e8e5543bdde65e86029e2fd9fc169899c440a7913
(4) add53f9a7e588d003326d1cbf9e4a43c061aadd9bc938c843a79e7b4fd2ad743
(5) 395df67f0c2d2d9fe1ad08d1bc8b6627011959b79c53d7dd6a3536a33ab8a4fd
(6) e485d098507f54e7733a205420dfddbe58db035fa577fc294ebd14db90767a52
(7) a453611d9419d0e56f499079478fd72c37b251a94bfde4d19872c44cf65386e3
(8) 829e924fdf021ba3dbbc4225edfece9aca04b929d6e75613329ca6f1d31c0bb4
(9) b0057716d5917badaf911b193b12b910811c1497b5bada8d7711f758981c3773

HD Wallet
==================
Mnemonic:      myth like bonus scare over problem client lizard pioneer submit female collect
Base HD Path:  m/44'/60'/0'/0/{account_index}

Listening on localhost:8545
```

It creates a new blockchain, starts an ethereum client with 10 accounts listenning
for ethereum json-rpc commands on localhost:8545 (127.0.0.1:8545).

You can then follow the docs but the short cut is do a `truffle migrate` and `truffle build`:
```
$ truffle migrate
Compiling ConvertLib.sol...
Compiling MetaCoin.sol...
Compiling Migrations.sol...
Writing artifacts to ./build/contracts
Running migration: 1_initial_migration.js
  Deploying Migrations...
  Migrations: 0xe78a0f7e598cc8b0bb87894b0f60dd2a88d6a8ab
Saving successful migration to network...
Saving artifacts...
Running migration: 2_deploy_contracts.js
  Deploying ConvertLib...
  ConvertLib: 0xcfeb869f69431e42cdb54a4f4f105c19c080a601
  Linking ConvertLib to MetaCoin
  Deploying MetaCoin...
  MetaCoin: 0x254dffcd3277c0b1660f6d42efbb754edababc2b
Saving successful migration to network...
Saving artifacts...
wink@wink-desktop:~/prgs/ethereum/truffle-init (master)
$ truffle build
```

And then use a browser to access the webpage created in build and then you can send
your "MetaCoin" to one of the other accounts:
```
$ chromium build/index.html
Created new window in existing browser session.
```

Below is the screenshot:
![Screenshot](https://github.com/winksaville/truffle-init/raw/master/screenshot.png "Screenshot")
