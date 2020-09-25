# Check Your Bag Twice

### Slot Locked

When doing bags and pouches you may think it's enough to just make `SlotLocked` and place the bag into it that is not true. Because how bad Minecraft handling containers `SlotLocked` will never work (see `Container#slotClick` when `ClickType` is `SWAP`. Moving items between hotbar and inventory). Surprisingly it's done very well in Thaumcraft. Thaumcraft's Wand Focus Pouch remembers in wich slot it's placed and disables interaction with this slot inside `Container#slotClick` method.

### Can Interact With

Don't just return true. If your bag can only been opened when held in hands check both hands. Always check if hand stack is empty first then compair it against stack assotiated with container.

### But Can You Actually Interact

You may think `canInteractWith` is enough. Wrong. The way clicks work require you to check every single one. `canInteractWith` is called every tick but `slotClick` is called every time click packet comes in. All packets handles in one queue so one packet can affect player's state that bag's container is no longer valid to interact with and next packet can be `slotClick` packet for this container but `canInteractWith` is not gonna be called until next tick so `slotClick` will be called on an invalid container. That's why you should check your item containers every time user clicks a slot.

It's however not a problem for containers assotiated with blocks and tileentities.


