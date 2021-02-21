Never transform access of protected members. If you make protected member public jvm will crash when trying to load subclass of transformed class because you cant override public method with protected modifier.

Example from [iChunUtil](https://github.com/iChun/iChunUtil) used by [Morph](https://github.com/iChun/Morph):
```
public net.minecraft.entity.Entity func_70105_a(FF)V #setSize
public net.minecraft.entity.EntityAgeable func_70105_a(FF)V #setSize
public net.minecraft.entity.monster.EntityZombie func_70105_a(FF)V #setSize
```
They transfrom each class they have in their dev env but they didn't think about us.

This is not a problem with private method because they can't be overriden.
