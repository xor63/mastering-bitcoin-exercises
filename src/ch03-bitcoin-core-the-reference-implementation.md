# 3. Bitcoin Core: The Reference Implementation

Chapter 3 of the book Mastering Bitcoin 2nd Edition is a highly technical
chapter for setting up a development environment. It walks you through compiling
Bitcoin Core and configuring/running your own node. If you follow the steps and
explore the help documentation as described in the chapter, there's more than
enough exercises to work on.

The last section of that chapter is Alternative Clients, Libraries and Toolkits.
It lists some libraries, clients and toolkits grouped by programming language.
We can work on exercises that use any of these to expand on this chapter. With
your programming language of choice, select the software in the list that you
would like to explore and see if you can do any of the exercises below.

### 3.1 Decode a raw transaction

Using a client library, decode Alice's coffee transaction with the following
transaction ID:

```
0627052b6f28912f2703066a912ea577f2ce4da4caa5a5fbd8a57286c345c2f2
```

Depending on the library, you may have to initially obtain a serialized
transaction that you will then have to decode, or you may directly get a
human-readable format of the transaction.

Check that you can see the same transaction inputs and outputs as in the book.

### 3.2 Find Alice's transaction in the block

In the book, we saw that Alice's transaction was included in block 277316. Using
a client library, obtain this block and find Alice's transaction in the list of
transactions that the block contains.

### 3.3 Execute `getmempoolinfo`

The book mentioned `getmempoolinfo` as one of the more important RPC commands.
Using the Bitcoin Core client or an alternative client library with a similar
command, execute this command and get the details of the memory pool such as the
minimum fee rate for a transaction to be accepted.
