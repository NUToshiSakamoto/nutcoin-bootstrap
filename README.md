# nutcoin-bootstrap

**bootstrap.dat** allows a new NutCoin client (not synced) to rapidly import the initial blocks from a local file instead of slowly downloading blocks from random peers. This significantly reduces the time it takes to get a client synced with the current blockchain.

Simply having bootstrap.dat in NutCoin's expected data directory will make your initial block sync much faster. The import process can be even faster if you use the `-dbcache=1000` command line parameter which uses an additional 1GB of RAM for the database index cache.

### Instructions

1.  Download [bootstrap.dat.zip](https://github.com/NUToshiSakamoto/nutcoin-bootstrap/releases/download/latest/bootstrap.dat.zip).
2.  Verify the integrity of bootstrap.dat.zip with the checksums.
3.  Decompress to obtain bootstrap.dat.
4.  Put it into the NutCoin datadir. This is the same folder that contains wallet.dat and the blocks folder.
5.  Delete bootstrap.dat.old if you want to recover some storage space.

### Verify integrity

##### **MD5** 
`6a2134604278f5826f90e46ff0a4006f  bootstrap.dat.zip`

##### **SHA256**
 `1ab7d056c1e2bc67adbc9cd4ea8351349e6a806529f12cafbf77890edc194b20  bootstrap.dat.zip`
  
### Copy **bootstrap.dat** to data directory

After NutCoin has used bootstrap.dat, the file will be renamed to bootstrap.dat.old; at this point you can choose to delete it or keep it.

##### **Linux**
  NutCoin's data directory is located in `~/.nutcoin/` by default. You can run `ls -a` to see directories that start with a dot.
  You can also search for the directory with the following command: `find / -name wallet.dat -print 2>/dev/null`


##### **Windows**
  Go to `Start>Run` (or press `WinKey+R`) and run: `explorer %APPDATA%\Nutcoin`
  NutCoin's data directory will open. "AppData" and "Application Data" are hidden by default in Windows.
  
### Data directory location

**Operating System** | **Default data directory location**  |  **Typical path to configuration file***
------------ | ------------- | -------------
Linux |  `$HOME/.nutcoin/`  |  `/home/<username>/.nutcoin/nutcoin.conf` 
Windows |  `%APPDATA%\Nutcoin\`  |  `C:\Users\<username>\AppData\Roaming\Nutcoin\nutcoin.conf` 

