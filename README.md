# BitcoinMiner-Esp8266


A bitcoin block miner using esp8266


## Index


- [Help](#help)

- [Info](#info)

- [Notes](#notes)

## Help

to mine a block/validate you just download the MinerBitcoin lib and
then include it in your main.ino, then create a `MinerBitcoin miner` object
then call the function for mining, if you wanted to be notified that it
was successfully mined, just turn on the led using the following function, `pinLight()` and `pinLow()`

> example

```C++

void setup() {

  MinerBitcoin miner;

  long long int tStamp = 0x2F0E95A638;
  int nBlock = 0;
  const char* Transactions = "satoshi->mob->fall";
  int Difficulty = 20;
  const char* pHash = "0000000000000000000987616aad095254ca83a34abd34c483057417c03dff6f";

  pinLight();
  miner.MinerBit(nBlock, Transactions,  pHash, tStamp, Difficulty);
  pinLow();

}

```
##### difficulty
by default the block mining difficulty is set to `4`
if you want to pass the difficulty
just pass the amount to `20` at the end of the function


##### Serial Port

if you wanted to edit the output of the Serial port,
just enter the code and go to
`#Port` in `MinerBitcoin.hpp` and put the port you want
by default the port is in `19200`


## Info


the code is under constant evaluation and testing... mining can be a little slow due to
the processing power of esp8266, i am always finding a way to optimize
the code and make it generate a hash (signature) faster.
for monitoring esp8266 job in command terminal execute `tail -f /dev/ttyUSB0` in linux.

## Notes

> I am not responsible if your esp8266 suffers consequences due to mining

> mining takes time

> code optimized for best mined

> removed logging
