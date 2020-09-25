# Breaking And Placing Blocks

### Placing

Bad example of placing blocks is [Botania's](https://github.com/Vazkii/Botania) Rannuncarpus it is cause of countless crashes. To place blocks you better use `EntityPlayerMP` or `FakePlayer`.
If you are using `FakePlayer` set it's held item to stack you want to use and then call `fakePlayer.interactionManager.processRightClick(...)` it will modify original stack. Don't forget to set fake player's hand to empty stack for sanity.

### Breaking

Use `PlayerInteractionManager#tryHarvestBlock`.
