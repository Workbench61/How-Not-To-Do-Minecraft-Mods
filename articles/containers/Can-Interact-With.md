# Can Interact With

When doing containers don't just leave `Container#canInteractWith` return `true` because you don't understand why this method exists.

### Common Dupes

Lets take a look at Blood Magic. For convinience get yourself a Teleposer setup. Place an Alchemy Table on teleposer put any items inside the table. Open table's GUI and activate Teleposer. Your table gets teleported but interface stays open. Now you can take items from it and then take them again from teleported table.

If you are not lonely you can have your frend to break the table while you looking inside it.

I actually don't remember if it works with Alchemy Table but it works with many containers from many mods but in different ways. Some drops container's items the correct way so you have to use Teleposer in order to dupe them.

Take a look at Bewitchment, Roots, Rustic, Astral Sorcery (recently fixed) and literally any other mod.

### How it works

Back to the Blood Magic. Take a look at `ContainerAlchemyTable` it has a method called `canInteractWith` which leads us all the way to `TileInventory#isUsableByPlayer` and all it does is just return `true`. Even vanilla Minecraft not this bad... Take a look at `TileEntityBrewingStand#isUsableByPlayer` it gets tile from the world and compares it with container's tile and then it checks the distance from player to brewing stand to be no more than 8 (eight) blocks.
