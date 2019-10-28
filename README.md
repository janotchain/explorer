# static-block-explorer

A simple static summary of the current and previous X blocks on the TRTL Network. Use this script to generate a static page for use on TOR or other networks where Javascript is not practical.

## Usage:

You will need a fully synced daemon running with the detailed block explorer output enabled.

#### Daemon:

```shell
TurtleCoind --enable-blockexplorer --enable-blockexplorer-detailed
```

This script will loop every 30 seconds, querying the daemon for results and writing a static file to the location of the Onion site you're hosting.

_Path and sleep time should be adjusted to match your preferences. The number of blocks you display can also be adjusted up to 30 by changing the last curl statement in `main.sh` to a different value ranging from `[0:0]` to `[0:30]`_

#### Shell:

```bash
while true; do ./main.sh > /var/www/tor/address.onion/index.html && sleep 30; done
```

## Example Output:

```bash
___                __
 |     ___|_ |  _ /   _  o __
 | |_| |  |_ | (/_\__(_) | | |
 Static Block Explorer
 github.com/turtlecoin/static-block-explorer


### CURRENT BLOCK ###
height - 1968281
network_height - 1968281
status - OK

### LAST BLOCK HEADER ###
block_size - 392
depth - 0
difficulty - 10887475102
hash - 952bdd8509c427a7676b8889d4fb77af4317f755c06aa4673d9126708001a6b8
height - 1968280
major_version - 6
minor_version - 0
nonce - 314889
num_txes - 1
orphan_status - false
prev_hash - 91f14c591a5f5b08d489b651fb1403c3218ba873e98a568ec5be22a49ae9c4ab
reward - 2810521
timestamp - 1572237740

### NETWORK INFO ###
alt_blocks_count - 0
difficulty - 10907541234
grey_peerlist_size - 1230
hashrate - 363584707
height - 1968281
incoming_connections_count - 7
last_known_block_index - 1968279
major_version - 6
minor_version - 0
network_height - 1968281
outgoing_connections_count - 8
start_time - 1572231828
status - OK
supported_height - 2000000
synced - true
tx_count - 2872654
tx_pool_size - 0
upgrade_heights - [187000,350000,440000,620000,700000,800000,1000000,1200000,1300000,1400000,1600000,1800000,2000000,2200000,2400000,2600000,2800000,3000000]
version - 0.20.0
white_peerlist_size - 80

### PENDING TRANSACTIONS ###
missed_tx - []
status - OK
txs_as_hex - []

### LAST 10 BLOCKS ###
[
  {
    "cumul_size": 392,
    "difficulty": 10887475102,
    "hash": "952bdd8509c427a7676b8889d4fb77af4317f755c06aa4673d9126708001a6b8",
    "height": 1968280,
    "timestamp": 1572237740,
    "tx_count": 1
  },
  {
    "cumul_size": 392,
    "difficulty": 10564869655,
    "hash": "91f14c591a5f5b08d489b651fb1403c3218ba873e98a568ec5be22a49ae9c4ab",
    "height": 1968279,
    "timestamp": 1572237712,
    "tx_count": 1
  },
  {
    "cumul_size": 7391,
    "difficulty": 10247650688,
    "hash": "4413b1c6aad9f0cb632a5c7c53b747e9bf59b8f316e0ec38d069e08de3fd19f9",
    "height": 1968278,
    "timestamp": 1572237707,
    "tx_count": 2
  },
  {
    "cumul_size": 392,
    "difficulty": 10360790301,
    "hash": "a9d112aa8143ae0b79358b6645b586307853bbbf00534ec8b2503c3a2a6862a6",
    "height": 1968277,
    "timestamp": 1572237703,
    "tx_count": 1
  },
  {
    "cumul_size": 392,
    "difficulty": 10019148844,
    "hash": "b8debab1f238c1f8f0d8b59a6e6d825e73552f6749aa115b5beed87f891b8b2a",
    "height": 1968276,
    "timestamp": 1572237664,
    "tx_count": 1
  },
  {
    "cumul_size": 16935,
    "difficulty": 10196379959,
    "hash": "4c83c731d39bd317f519bf7b8a6929740404fd4c53cac538b86f08ac921d0cfe",
    "height": 1968275,
    "timestamp": 1572237663,
    "tx_count": 3
  },
  {
    "cumul_size": 392,
    "difficulty": 9953294797,
    "hash": "23e37293e9bd75ebb300f6ac2aeedae471cb8334fb352362b9acd7172015fcf9",
    "height": 1968274,
    "timestamp": 1572237618,
    "tx_count": 1
  },
  {
    "cumul_size": 4109,
    "difficulty": 9754067622,
    "hash": "719d4094fb997f4db7cafd512d8c3c1ffd2dc1bd96bae2ead7e392f1636ba98c",
    "height": 1968273,
    "timestamp": 1572237609,
    "tx_count": 2
  },
  {
    "cumul_size": 13224,
    "difficulty": 9654375431,
    "hash": "39e6c3b4e99aa08eabcc018892d14b9b1948177c2a133d2c8572260c17cfd380",
    "height": 1968272,
    "timestamp": 1572237597,
    "tx_count": 4
  },
  {
    "cumul_size": 392,
    "difficulty": 9411781842,
    "hash": "c638ed36b326d4fc0ea9719dc300923ec6218d69af20b2c6849210483849b538",
    "height": 1968271,
    "timestamp": 1572237578,
    "tx_count": 1
  }
]


Made with <3 by the TurtleCoin Team
TurtleCoin(tm) 2017-2020
github.com/turtlecoin/static-block-explorer
```
