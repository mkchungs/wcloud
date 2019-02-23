# Wolk Cloudstore CLI

```
Wolk Cloudstore CLI:

Names/Accounts:
  GetName:      wcloud getname  name                     (returns address)
  SetName:      wcloud setname  name                     (same as mkdir wolk://owner)

  CreateAccount:wcloud createaccount name                (creates keys in ~/.wolk/name directory)
  SetDefault:   wcloud setdefault name                   (sets default name in ~/.wolk/name directory)

File Buckets:
  Make Bucket:  wcloud mkdir wolk://owner/bucket
  List Buckets: wcloud ls    wolk://owner                (same as ls wolk://owners/buckets/SCAN)
  Delete Bucket:wcloud rmdir wolk://owner/bucket         (same as rm wolk://owners/buckets/bucket)
  Put File:     wcloud put   localfile wolk://owner/bucket/file  (same as setkey wolk://owner/bucket/file @localfile)
  Get File:     wcloud get   wolk://owner/bucket/file localfile  (same as getkey wolk://owner/bucket/file)
  Delete File:  wcloud rm    wolk://owner/bucket/file
  List Bucket:  wcloud ls    wolk://owner/bucket/

NoSQL Collections:
  + Collection: wcloud createcoll wolk://owner/collection  (same as setkey wolk://owner/buckets/collection)
  Scan Colls:   wcloud scancolls  wolk://owner/            (same as ls wolk://owner/buckets/SCAN)
  - Collection: wcloud dropcoll   wolk://owner/collection  (same as rm wolk://owner/buckets/collection)
  Set Key:      wcloud setkey     wolk://owner/collection/key val
  Get Key:      wcloud getkey     wolk://owner/collection/key
  Delete Key:   wcloud rm         wolk://owner/collection/key
  Scan:         wcloud scan       wolk://owner/collection/ (same as ls wolk://owner/collection/SCAN)

SQL Databases:
  *Create DB:    wcloud createdb wolk://owner/database    (same as mkdir wolk://owner/database)
  *Show DBs:     wcloud showdbs  wolk://owner/            (same as ls    wolk://owner/buckets/SCAN)
  *Drop DB:      wcloud dropdb   wolk://owner/database    (same as rm    wolk://owner/buckets/database)
  *Show Tables:  wcloud sql      wolk://owner/database  "SHOW TABLES"
  *Create Table: wcloud sql      wolk://owner/database  "CREATE TABLE tablename ..."
  *Drop Table:   wcloud sql      wolk://owner/database  "DROP TABLE tablename"
  *Mutate:       wcloud sql      wolk://owner/database  "INSERT into tablename ..."
  *Read:         wcloud sql      wolk://owner/database  "SELECT * from tablename ..."

Blockchain:
  GetLatestBlock:  wcloud blocknumber                  (curl /wolk/latest/blocknumber]
  GetBalance:      wcloud balance address|name         (curl /wolk/balance/address]
  GetBlock:        wcloud block blocknumber               [curl /wolk/block/blocknumber]
  GetTransaction:  wcloud tx  txhash                      [curl /wolk/tx/txhash]
  GetNode:         wcloud node nodenumber                 [curl /wolk/node/nodenumber]
  GetNumPeers:     wcloud peers                           [curl /wolk/peers]
  Transfer:        wcloud transfer recipientaddr amount
 *RegisterNode:    wcloud registernode [nodenumber] [storageip] [consensusip] [region] [value]
 *UpdateNode:      wcloud updatenode registernode [nodenumber] [storageip] [consensusip] [region] [value]
 *BandwidthCheck:  wcloud bandwidthcheck [checkChunkHash]

File: [debugging only]
  Store:        wcloud add   localfile                    (returns filehash)
  Retrieve:     wcloud cat   filehash

Chunk: [debugging only]
  GetChunk:     wcloud getchunk chunkhash                 [curl /wolk/chunk/chunkhash]
  SetChunk:     wcloud setchunk file                      [curl /wolk/chunk/]

Share: [debugging only]
  GetShare:     wcloud getshare chunkhash                 [curl /wolk/share/chunkhash]
  SetShare:     wcloud setshare file                      [curl /wolk/share/]

Arguments: (optional)
  -server=node.url [all]
  -httpport=80
  -range=80-160    [cat]
  -maxcontentlength=1000000    [createcoll, createdb, mkdir, getkey, get, sql]
  -requesterpays=0 [createcoll, createdb, mkdir]
  -writers=0x1234...,0xabcd... [createcoll, createdb, mkdir]
  -name=someone
  -proof=true      [getkey, get, getname, sql]
  -blocknumber=23  [balance, node, getkey, getname, sql]
  -history=true    [getkey]

  (*: Not implemented/tested yet)

  ```

