# About

This is collection of common mistakes that many modders do.

# Straight into it

- Use `isDead`

This is the first rule of the cool club.

Always check for removed entities when dealing with them. The lack of this check is the reason for countless dupes. Even Minecraft devs forget to check for removed entities. Examples are dupe of any item using item frame and dupe of cows when shearing Mooshroom.

More on that in the [article](articles/entities/isDead.md)

- Never trust a client

When dealing with network packets always check the data you getting from client.

- If you are not sure how to implement your idea check how [Botania](https://github.com/Vazkii/Botania) does it.

Exceptions are Rannuncarpus placing blocks and Bore Lens breaking blocks.

# Articles

- [Entities](articles/entities)
 - [isDead](articles/entities/isDead.md)
 - [Drop The Items](articles/entities/Drop-The-Items.md)
- [Networking](articles/networking)
 - [Never Trust a Client](articles/networking/Never-Trust-a-Client.md)
- [Gui/Containers](articles/containers)
 - [Can Iteract With](articles/containers/Can-Interact-With.md)
