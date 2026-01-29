# ItemRack

If your mount is no longer detected by ItemRack, please do the following - 
1. Run this macro in game while you are mounted,
```
/run for i=1,32 do local t,_,g=UnitBuff("player",i);if not t then break end print(t,g) end
```
2. Screenshot what the macro prints and the tooltip of the buff you have while mounted,
3. Either paste your screenshot into an issue here or @McPewPew on the TurtleWoW Discord,
4. While you wait patiently for me to add your mount, you can try this in the meantime - 
copy/paste the code below into your Mount event, replacing the existing text,
```
local mount
if UnitIsMounted then mount = UnitIsMounted("player") else mount = ItemRack_PlayerMounted(true) end
if not IR_MOUNT and mount then
  EquipSet()
elseif IR_MOUNT and not mount then
  LoadSet()
end
IR_MOUNT=mount
--[[Equips set to be worn while mounted.]]
```
<img width="1566" height="933" alt="image" src="https://github.com/user-attachments/assets/9aa10ed9-d70d-4e0d-b361-a0fc9be86a30" />
While this *should* hopefully work, it's a lot less efficent.

### Mount Event Reliability (Turtle WoW)  
Mount detection via spell IDs with improved fallback handling.  
***New event*** – "Mount(Not ZG/AQ)" set switching when mounting, but disabled in AQ and ZG.

### Goblin Brainwashing Device Support  
Automatically set switch when using the Goblin Brainwashing Device.  
***New events*** – "Brainwashing 1-4" activate the event for each specialization.

<br>
<br>

If you want to use ItemRackFu, drag the ItemRackFu folder into the main Addons folder.

##
Mounting improvements and GBD support with assistance from [Sleepybear](https://github.com/McPewPew/ItemRack/pull/13/changes/bbc8d6ea784373ffa5c4c2a7325c40bb62bd9fd5)
