# Thread Safe

If you run async code that eventually should interact with Minecraft world do it properly.

Take a look at [Nevermine](https://github.com/Tslat/Advent-Of-Ascension/) here you find a `CoralStafTask` that removes blocks from the world after a given time. It's shcedules from `ScheduledExecutorService` and will eventually run on it's thread and this is incorrect. When running world interaction from other thread you should somehow obtain a World instance or MinecraftServer instance and call `addScheduledTask` on it. Place your logic in the `Runnable` and it will run on the correct thread as soon as possible.
