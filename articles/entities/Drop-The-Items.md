# Drop The Items

If your entity has an inventory and you want to drop its content on entity's death you need to do this correctly. That means before/after dropping the stack you need to set its previous holder to empty.

### Donkey item dupe

To do this dupe you have to have Twilight Forest installed. Get a chested donkey place any items in its chest and also put a Life Charm in there. Kill the donkey. It drops its items and also stays alive because of Life Charm. Repeat.

The missing code in `AbstractHorse#onDeath` method. It only drops contents of `horseChest` but never replaces it with empty stacks.

But actually this dupe works because of Forge doing events wrong...
