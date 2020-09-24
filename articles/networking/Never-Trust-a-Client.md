# Never Trust a Client

When dealing with network always check data you gets from client.

### Is Area Loaded

Go grab some McJtyLib because even devs like McJty could miss obvious things. They fixed this vulnerability only in autumn of 2020 (twenty twenty) so it still exists in 1.12 version of the mod. Take a look at `PacketDumpBlockInfo#handle` method here is call to `DumpBlockNBT.dumpBlockNBT` static method. Finally it calls `World#getTileEntity` and `World#getBlockState` those two methods will load chunks at given coordinates. Loading chunks is expensive task and if you read official Forge documentation you will know that you always should call `World#isBlockLoaded` before calling `World#getTileEntity` when dealing with network. And this check is missed in all McJty's mods.
