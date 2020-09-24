# isDead

When messing with entities it is always important to check for removed ones. Missing this check can lead to various dupes and missbehaviors.
Lets take a look at some.

### Item Frame duplication glitch

There are actually two mistakes in one place.

To do the dupe you need to place piston horizontally and hang an item frame on its back. Place an item you want to dupe in the frame then power the piston and quiqly punch the item frame. In result you will have item from the frame dropped twice onece from destruction of the frame caused by piston state update and second time cause you punched it.

When piston changes its state item frame no longer recognize it as a valid surface to hang on and it drops sets the `removed` flag to true on itself. It also drops the displayed item but it does it the way that it actually stays in the frame (see [Drop-The-Items](Drop-The-Items.md)). Then attack packet from player comes in and methond `attackEntityFrom` called but it misses the check for removed item frames and drops displayed item again.
